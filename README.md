# Kind-Shredder

Secure storage solution - 

-  The File upload API(s) in this software allow end-users to upload a file which is ...
    - Encrypted with AES algorithm against an user provided password
    - Broken into chunks of confugurable size
    - Each chunk is randomly stored in a GCP cloud storage bucket
    - The storage map is stored in PostgreSQL
    - Returns a unique hash, which can later be used to retreive the file
    
-  The File Retreival API
    - Needs to be called with the unique hash as a URL param
    - Fetches the file-chunk-storage map from DB
    - Downloads the individual chunks from GCP storage bucket
    - Decrypts the File with the provided password
    - Returns a download link for the file
