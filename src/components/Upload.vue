<template>
    <div class="uw">
      <h3>Upload Widget Example</h3>
      <button v-on:click="open" id="upload_widget" class="cloudinary-button">
        Upload files
      </button>
      <p>
        <a
          href="https://cloudinary.com/documentation/upload_widget"
          target="_blank"
          >Upload Widget User Guide</a
        >
      </p>
      <p>
        <a
          href="https://cloudinary.com/documentation/upload_widget_reference"
          target="_blank"
          >Upload Widget Reference</a
        >
      </p>
    </div>
  </template>
  
  <script>
  const cloudName = "hzxyensd5"; // replace with your own cloud name
  const uploadPreset = "aoh4fpwm"; // replace with your own upload preset
  
  // Remove the comments from the code below to add
  // additional functionality.
  // Note that these are only a few examples, to see
  // the full list of possible parameters that you
  // can add see:
  //   https://cloudinary.com/documentation/upload_widget_reference
  
  const myWidget = cloudinary.createUploadWidget(
    {
      cloudName: cloudName,
      uploadPreset: uploadPreset,
      // cropping: true, //add a cropping step
      // showAdvancedOptions: true,  //add advanced options (public_id and tag)
      // sources: [ "local", "url"], // restrict the upload sources to URL and local files
      // multiple: false,  //restrict upload to a single file
      // folder: "user_images", //upload files to the specified folder
      // tags: ["users", "profile"], //add the given tags to the uploaded files
      // context: {alt: "user_uploaded"}, //add the given context data to the uploaded files
      // clientAllowedFormats: ["images"], //restrict uploading to image files only
      // maxImageFileSize: 2000000,  //restrict file size to less than 2MB
      // maxImageWidth: 2000, //Scales the image down to a width of 2000 pixels before uploading
      // theme: "purple", //change to a purple theme
    },
    (error, result) => {
      if (!error && result && result.event === "success") {
        console.log("Done! Here is the image info: ", result.info);
        document
          .getElementById("uploadedimage")
          .setAttribute("src", result.info.secure_url);
      }
    }
  );
  
  export default {
    name: "UploadWidget",
    data: () => ({
      open: function () {
        myWidget.open();
      },
    }),
    props: {
      msg: String,
    },
  };
  </script>
  
  