### Check the signature of a keystore or an APK without extracting any files.

- Signature of an APK
```
keytool -list -printcert -jarfile app.apk
```
The output will reveal the signature owner/issuer and MD5, SHA1 and SHA256 fingerprints of the APK file app.apk.
(Note that the -jarfile argument was introduced in Java 7; see the documentation for more details.)

- Signature of a keystore
```
keytool -list -v -keystore release.jks
```
The output will reveal the aliases (entries) in the keystore file release.jks, with the certificate fingerprints (MD5, SHA1 and SHA256).
If the SHA1 fingerprints between the APK and the keystore match, then you can rest assured that that app is signed with the key.


Reference:
https://stackoverflow.com/questions/11331469/how-do-i-find-out-which-keystore-was-used-to-sign-an-app
