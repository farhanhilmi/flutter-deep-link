# Instruction Flutter App Link

Official documentation about flutter `firebase_core` and `firebase_dynamic_links` :

-   https://pub.dev/packages/firebase_core
-   https://pub.dev/packages/firebase_dynamic_links

### Install package

```
- flutter pub add firebase_dynamic_links
- flutter pub add firebase_core
```

### Update lib/main.dart

inside main function

```
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp();
  runApp(const MyApp());
}
```

---

<br><br>

# In Server

For more information: https://simonmarquis.github.io/Android-App-Linking/app-links/

### Create well-known directory in server root

-   create `assetlinks.json` file
-   store this code in that file
    ```
    [
      {
          "relation": [
              "delegate_permission/common.handle_all_urls"
          ],
          "target": {
              "namespace": "android_app",
              "package_name": "com.example.test_project",
              "sha256_cert_fingerprints": [
                  "6B:41:26:A6:1E:D8:BD:91:D3:8B:57:10:5F:07:5C:2D:AB:3E:26:A4:D1:3C:9C:97:15:78:9E:0D:56:0A:CE:DC"
              ]
          }
      }
    ]
    ```
-   To get cert fingerprints, type `gradlew signingReport` inside `android` folder
