# 🔐 Flutter Biometric Authentication App
A Flutter-based mobile application that demonstrates secure user authentication using biometric features (fingerprint/face unlock) along with session management using `SharedPreferences`.


## 📱 Screenshots

| Login Screen               | Homepage                      | Screenshot Block |
![WhatsApp Image 2025-07-02 at 09 21 18_892842d7](https://github.com/user-attachments/assets/18737600-e262-4195-b83e-825fe8be974a)
![WhatsApp Image 2025-07-02 at 09 21 18_2bb46856](https://github.com/user-attachments/assets/ccb40279-f0cf-4a63-bc95-38fe04ea4bcd)
![WhatsApp Image 2025-07-02 at 09 53 29_346ae762](https://github.com/user-attachments/assets/aebb8d28-38d8-4704-93e2-b72e0e067f6d)

> 📌 Note: Taking screenshots on some secured screens is blocked due to app security policy.
## 🚀 Features
- User login with email & password
- Persistent login state using `SharedPreferences`
- Biometric Authentication (Fingerprint/Face unlock)
- Option to setup biometric login
- Logout functionality
- Clean and dark-themed UI


## 📦 Dependencies
| Package               | Version |
|:----------------------|:---------|
| `flutter`             | `>=3.22.0` |
| `shared_preferences`  | `^2.2.2` |
| `local_auth`          | `^2.2.0` |


## 📂 Project Structure
lib/
┣ biometricauth.dart
┣ main.dart
┣ screens/
┃ ┣ login_screen.dart
┃ ┗ home_screen.dart
