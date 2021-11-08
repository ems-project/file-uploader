# file-uploader
NPM module that upload a file chunk by chunk


## Usage

```javascript
        const fileUploader = new FileUploader({
            file: file,
            algo: 'sha1',
            initUrl: 'https://server/data/file/init-upload',
            onHashAvailable: function(hash, type, name){
                console.log('A file has been identified by its hahs: '+hash);
            },
            onProgress: function(status, progress, remaining){
                const percentage = Math.round(progress*100);
                console.log(''+percentage+ '% of the file has been uploaded');
            },
            onUploaded: function(assetUrl, previewUrl){
                console.log('A file has been uploaded and is available here '+assetUrl);
            },
            onError: function(message, code){
                console.log('An error appends');
                console.log(message, code);
            },
        });
    }
```