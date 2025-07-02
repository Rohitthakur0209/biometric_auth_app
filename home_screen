import 'package:biometric_auth_app/screens/login_screen.dart';
import 'package:flutter/material.dart';
import 'package:shared_preferences/shared_preferences.dart';
import 'package:biometric_auth_app/biometricauth.dart';


class Homepage extends StatefulWidget {
  const Homepage({super.key});

  @override
  State<Homepage> createState() => _HomepageState();
}

class _HomepageState extends State<Homepage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Welcome to the homepage'),

            // 👇 Add a button to navigate to the login screen
            ElevatedButton(
              onPressed: () {
                Navigator.push(context,
                    MaterialPageRoute(builder: (context) => LoginScreen()));
              },
              child: Text('Login'),
            ),

            //logout button

            ElevatedButton(
              onPressed: () async {
                final Future<SharedPreferences> prefs =
                SharedPreferences.getInstance();
                prefs.then((SharedPreferences prefs) {
                  prefs.setBool('isloggedin', false);
                  prefs.setBool('isbiometricenabled', false);
                });
                Navigator.push(context,
                    MaterialPageRoute(builder: (context) => LoginScreen()));
              },
              child: Text('Logout'),
            ),

            //setup authentication button
            //setup authentication button
            ElevatedButton(
              onPressed: () async {
                Biometricauth()
                    .checkBiometric(context, Homepage(), LoginScreen(), true);
              },
              child: Text('Setup Authentication'),
            ),
          ],
        ),
      ),
    );
  }
}
