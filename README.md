# spotify_sdk_example

⚠️ Demonstrates how the spotify is not working with `flutter_background_service`(https://pub.dev/packages/flutter_background_service) plugin

First check this in working condition by running as it is. Then second time, uncomment the following line of code in `main()` then try to get the error.

```sh
Future<void> main() async {
WidgetsFlutterBinding.ensureInitialized();
///TODO: Calling This Func Is Stopping The Spotify Player in IOS, Comment This To Play Properly
/// Not Working In Android 13 Either With Or Without The Below Code
await initializeService();
await dotenv.load(fileName: '.env');
runApp(const Home());
}
```

Before running the app you have to edit the `.env` file in the root of the example project and add your own `CLIENT_ID` and `REDIRECT_URL` without surrounding quotes. Make sure that you don't push your credentials to a public repository.

If running on iOS you need to open the Xcode project and set the development team, bundle ID and the redirect URL scheme under "URL Types" as stated in the Spotify iOS SDK documentation.

```sh
CLIENT_ID=YOUR_CLIENT_ID
REDIRECT_URL=YOUR_REDIRECT_URL
```

Also check that it is not working in Android also.

```sh
# Extra Plugins We Used
flutter_background_service: ^5.0.1
shared_preferences: ^2.2.0
device_info_plus: ^9.0.3
flutter_local_notifications: ^15.1.1
``