# Running MobSF With Docker on GAEN-mobile


1. Create Zip archives for the ios app and android app
    * Download the GAEN-mobile project from https://github.com/Path-Check/gaen-mobile
    * Create a ZIP archive of the ios/ and android/app/ directories
2. Download the MobSF docker image using the following command
   
    ```docker pull opensecurity/mobile-security-framework-mobsf```
3. Start MobSF using the following command:
   
   ```docker run -it --rm -p 8000:8000 opensecurity/mobile-security-framework-mobsf:latest```
4. Upload the zipped files in your browser at http://localhost:8000