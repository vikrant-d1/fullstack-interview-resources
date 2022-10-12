# React-codeblocks
> Important code blocks
### Table of Contents

| No. | Questions |
| --- | --------- |
|1  | [Get Check if an Element is in the Viewport in React.js?](#Get-Check-if-an-Element-is-in-the-Viewport-in-React.js) |
|2  | [Use portal for popup](#Use portal for popup) |
|3  | [Use use form hook](#Use use form hook) |
|4  | [Image compress](#Image compress) |


### 1.Get Check if an Element is in the Viewport in React.js
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

**[⬆ Back to Top](#table-of-contents)**
