# React-codeblocks
> Important code blocks
### Table of Contents

| No. | Questions |
| --- | --------- |
|1  | [Get Check if an Element is in the Viewport in React.js?](#1.-Get-Check-if-an-Element-is-in-the-Viewport-in-React.js) |
|2  | [Use portal for popup?](#2-Use-portal-for-popup) |
|3  | [Use use form hook?](#3-Use-use-form-hook) |
|4  | [Image compress?](#4-Image-compress) |


### 1. Get Check if an Element is in the Viewport in React.js
```javascript
import {useEffect, useRef, useState, useMemo} from 'react';

export default function App() {
  const ref1 = useRef(null);
  const ref2 = useRef(null);

  const isInViewport1 = useIsInViewport(ref1);
  console.log('isInViewport1: ', isInViewport1);

  const isInViewport2 = useIsInViewport(ref2);
  console.log('isInViewport2: ', isInViewport2);

  return (
    <div>
      <div ref={ref1}>Top div {isInViewport1 && '| in viewport ✅'}</div>

      <div style={{height: '155rem'}} />

      <div ref={ref2}>Bottom div {isInViewport2 && '| in viewport ✅'}</div>
    </div>
  );
}

function useIsInViewport(ref) {
  const [isIntersecting, setIsIntersecting] = useState(false);

  const observer = useMemo(
    () =>
      new IntersectionObserver(([entry]) =>
        setIsIntersecting(entry.isIntersecting),
      ),
    [],
  );

  useEffect(() => {
    observer.observe(ref.current);

    return () => {
      observer.disconnect();
    };
  }, [ref, observer]);

  return isIntersecting;
}

```
### Why use the heigh ordered component in the react?
Higher-order components (HOCs) are a useful pattern in React for code reuse and component composition. HOCs are functions that take in a component and return a new component with some additional functionality or behavior.

There are several reasons why you might want to use HOCs in your React application:

Reusability: HOCs can be reused across different components and projects, reducing code duplication and improving maintainability.

Composition: HOCs can be composed together to create more complex components with multiple layers of functionality.

Separation of Concerns: HOCs can be used to separate concerns, such as logic for fetching data, authentication, or handling error messages, from the presentation layer of a component.

Code organization: HOCs can help organize your codebase by encapsulating functionality that can be applied to multiple components.

Code sharing: HOCs can be shared across teams or even open-sourced for other developers to use in their applications.

Overall, using HOCs can help make your codebase more modular, reusable, and maintainable, which can lead to faster development cycles and better code quality.

### how to use Suspense in react?
Suspense is a new feature introduced in React 16.6 that allows components to suspend rendering while they asynchronously fetch data. This can help improve the perceived performance of your application by reducing the amount of time users spend waiting for data to load.

Here's how you can use Suspense in React:

1. Wrap the component(s) that need to asynchronously fetch data in a Suspense component. The Suspense component should have a fallback prop that defines what to render while the component is waiting for data.
```javascript
import React, { Suspense } from 'react';

function MyComponent() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <AsyncComponent />
    </Suspense>
  );
}
```
2. Create an asynchronous component that returns a promise. This component will be loaded asynchronously and will not block the main thread.

const AsyncComponent = React.lazy(() => import('./AsyncComponent'));

3. In the AsyncComponent module, define the component that should be rendered after the data has been fetched.

```javascript
function AsyncComponent() {
  const data = fetchData(); // asynchronous data fetching
  return <div>{data}</div>;
}
```







### 2. Use portal for popup
```javascript
import { createPortal } from "react-dom";

<div id="#camera-modal"></div>

***id plase in _document.js file***

 {otpModalStatus && createPortal(<ProfileUpdateOtpVerification openModal={otpModalStatus} profileStatus={true} phoneNumber={is_mobile_verified} countryCode={phone_code} otpPopup={setOtpModalStatus} email={is_email_verified} setOtpStatus={setOtpStatus} />, document.querySelector('#camera-modal'))}
```

### 3. Use use form hook

```javascript
import { useForm } from 'react-hook-form';

  const { register, handleSubmit, setValue, reset, watch, formState: { errors },
  } = useForm();
    const watchAllFields = watch(); // when pass nothing as argument, you are watching everything
     const watchImages = watch(["images"]); 
  
  //set value in inpute field
  const handleEditClick = (contact) => {
      setEditContactId(contact.id);
      setValue('id',contact.id);
  };
  
  const cameraSubmit = (data) => {
    setLoadingStatus(true);
    if (editContactId) {
      const newContacts = [...contacts];
      updateCamera(data);
      setContacts(newContacts);
    } else {
      setEditContactId(null);
      addCamera(data);
    }
  };
  
  
    <form onSubmit={handleSubmit(cameraSubmit)} >
 
        <input
          type="text"
          className="field_info"
          {...props?.register("name",{ required: true })}
        />
        {props?.errors?.name && <p className={'text-danger mt-1'}>Name is required.</p>}
    
        <input
          type="text"
          className="field_info"
          {...props?.register("location")}
        />
        
      
        <input
          type="text"
          className="field_info"
          {...props?.register("longitude",{ required: true, pattern:/^(\-?\d+(\.\d+)?)/g })}
        />
        {props?.errors?.longitude && <p className={'text-danger mt-1'}>Longitude is required.</p>}
    
        <input
          type="text"
          className="field_info"
          {...props?.register("latitude",{ required: true, pattern: /\w*(\-?\d+(\.\d+)?)$/g })}
        />
          {props?.errors?.latitude && <p className={'text-danger mt-1'}>Latitude is required.</p>}
     
        <span className="table_ico" onClick={()=>props?.locationTogglePopup()}>
          <MapOutline />
        </span>
     
        <input
          type="url"
          name="url"
          className="field_info"
          {...props?.register("url",{ required: true , pattern: /(https?:\/\/)?([\da-z\.-]+)\.([a-z]{2,6})([\/\w\.-]*)*\/?/g})}
        />
      {props?.errors?.url && <p className={'text-danger mt-1'}>Url is required.</p>}
    
     </form>
```
### 4. Image compress

```javascript

import Compressor from 'compressorjs';

 new Compressor(uploaded_file, {
        quality: 0.6,
        success(result) {
          let blobTofile = new File([result], result.name, {type: result?.type, lastModified: Date.now()});
          setSelectedOriginalImage(URL.createObjectURL(blobTofile));
          files.push({ image: fileData, type: "image" });
        },
        error(err) {
          dispatch(
            Notify.setNotification({
              message: err.message,
              type: "error",
            })
          );
        },
      });

```

### 5. Data url to file

```javascript
export function dataURLtoFile(dataurl, filename) {
  var arr = dataurl.split(","),
    mime = arr[0].match(/:(.*?);/)[1],
    bstr = atob(arr[1]),
    n = bstr.length,
    u8arr = new Uint8Array(n);

  while (n--) {
    u8arr[n] = bstr.charCodeAt(n);
  }
  return new File([u8arr], `${filename}.${mime.split("/")[1]}`, { type: mime });
}
```


### 5. File to base64

```javascript
export const getBase64 = (file) => {
  return new Promise((resolve, reject) => {
    const reader = new FileReader();
    reader.readAsDataURL(file);
    reader.onload = () => resolve(reader.result);
    reader.onerror = (error) => reject(error);
  });
};
```

### Video file to thumbnail creator

```javascript 
export const getVideoCover = (file, seekTo = 0.0) => {
  return new Promise((resolve, reject) => {
    const videoPlayer = document.createElement("video");
    videoPlayer.setAttribute("src", URL.createObjectURL(file));
    videoPlayer.load();
    videoPlayer.addEventListener("error", (ex) => {
      reject("error when loading video file", ex);
    });
    videoPlayer.addEventListener("loadedmetadata", () => {
      if (videoPlayer.duration < seekTo) {
        reject("video is too short.");
        return;
      }
      setTimeout(() => {
        videoPlayer.currentTime = seekTo;
      }, 200);
      videoPlayer.addEventListener("seeked", () => {
        const canvas = document.createElement("canvas");
        canvas.width = videoPlayer.videoWidth;
        canvas.height = videoPlayer.videoHeight;
        const ctx = canvas.getContext("2d");
        ctx.drawImage(videoPlayer, 0, 0, canvas.width, canvas.height);
        ctx.canvas.toBlob(
          (blob) => {
            resolve(blob);
          },
          "image/jpeg",
          0.75
        );
      });
    });
  });
};
```
### Rename Uploaded file

```javascript
export const renameFile = (originalFile) => {
  let d = new Date();
  let filetype = originalFile.type;
  const [ft, fileEx] = filetype.split("/");
  if (fileEx == "quicktime") {
    fileEx = "mov";
  }
  let newName = d.getTime();
  return new File([originalFile], newName + "." + fileEx, {
    type: originalFile.type,
    lastModified: originalFile.lastModified,
  });
};
```

### Detect Browser

```javascript
export const browserDetect = () => {
  let userAgent = navigator.userAgent;
  let browserName;
  if (userAgent.match(/chrome|chromium|crios/i)) {
    browserName = "chrome";
  } else if (userAgent.match(/firefox|fxios/i)) {
    browserName = "firefox";
  } else if (userAgent.match(/safari/i)) {
    browserName = "safari";
  } else if (userAgent.match(/opr\//i)) {
    browserName = "opera";
  } else if (userAgent.match(/edg/i)) {
    browserName = "edge";
  } else {
    browserName = "No browser detection";
  }
  return browserName;
};

```




**[⬆ Back to Top](#table-of-contents)**
