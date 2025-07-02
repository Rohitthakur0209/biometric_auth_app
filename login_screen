import 'package:flutter/material.dart';
import 'package:shared_preferences/shared_preferences.dart';
import 'package:biometric_auth_app/screens/home_screen.dart';
import 'package:biometric_auth_app/biometricauth.dart'; // assuming this is your biometric utility

class LoginScreen extends StatefulWidget {
  @override
  State<LoginScreen> createState() => _LoginScreenState();
}

class _LoginScreenState extends State<LoginScreen> {
  TextEditingController emailController = TextEditingController();
  TextEditingController passwordController = TextEditingController();

  void _loginuser() async {
    final SharedPreferences prefs = await SharedPreferences.getInstance();

    await prefs.setBool('isloggedin', true);

    Navigator.pushReplacement(
      context,
      MaterialPageRoute(builder: (context) => Homepage()),
    );
  }

  bool showbiometric = false;

  @override
  void initState() {
    super.initState();
    _checkBiometricStatus();
  }

  void _checkBiometricStatus() async {
    final SharedPreferences prefs = await SharedPreferences.getInstance();
    bool isloggedin = prefs.getBool('isloggedin') ?? false;
    bool isbiometricenabled = prefs.getBool('isbiometricenabled') ?? false;

    setState(() {
      showbiometric = isloggedin && isbiometricenabled;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SingleChildScrollView(
        child: Container(
          height: MediaQuery.of(context).size.height,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [
                Colors.black,
                Colors.grey[900]!,
              ],
              begin: Alignment.topLeft,
              end: Alignment.bottomRight,
            ),
          ),
          child: Column(
            children: [
              Expanded(
                child: Container(
                  decoration: BoxDecoration(
                    borderRadius: const BorderRadius.only(
                      topLeft: Radius.circular(30),
                      topRight: Radius.circular(30),
                    ),
                    gradient: LinearGradient(
                      colors: [
                        Colors.black,
                        Colors.grey[900]!,
                      ],
                      begin: Alignment.topLeft,
                      end: Alignment.bottomRight,
                    ),
                  ),
                  child: Padding(
                    padding: const EdgeInsets.all(20),
                    child: Column(
                      mainAxisAlignment: MainAxisAlignment.center,
                      crossAxisAlignment: CrossAxisAlignment.stretch,
                      children: [
                        const Text(
                          'Sign In',
                          style: TextStyle(
                            fontSize: 32,
                            fontWeight: FontWeight.bold,
                            color: Colors.white,
                          ),
                        ),
                        const SizedBox(height: 30),
                        TextField(
                          controller: emailController,
                          decoration: InputDecoration(
                            fillColor: Colors.white,
                            hintText: 'Email',
                            prefixIcon: const Icon(Icons.email),
                            border: OutlineInputBorder(
                              borderRadius: BorderRadius.circular(10),
                            ),
                          ),
                        ),
                        const SizedBox(height: 20),
                        TextField(
                          controller: passwordController,
                          obscureText: true,
                          decoration: InputDecoration(
                            hintText: 'Password',
                            prefixIcon: const Icon(Icons.lock),
                            border: OutlineInputBorder(
                              borderRadius: BorderRadius.circular(10),
                            ),
                          ),
                        ),
                        const SizedBox(height: 20),
                        ElevatedButton(
                          onPressed: () {
                            print("login button pressed");
                            _loginuser();
                          },
                          child: const Text('Sign In'),
                          style: ElevatedButton.styleFrom(
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.circular(10),
                            ),
                            padding: const EdgeInsets.symmetric(vertical: 15),
                          ),
                        ),
                        const SizedBox(height: 20),
                        ElevatedButton(
                          onPressed: () {
                            // Sign up logic
                          },
                          child: const Text('Sign Up'),
                          style: ElevatedButton.styleFrom(
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.circular(10),
                            ),
                            padding: const EdgeInsets.symmetric(vertical: 15),
                          ),
                        ),
                        const SizedBox(height: 20),
                        showbiometric
                            ? GestureDetector(
                          onTap: () => Biometricauth().checkBiometric(
                              context, Homepage(), LoginScreen(), false),
                          child: Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            children: const [
                              Icon(
                                Icons.fingerprint,
                                color: Colors.white,
                              ),
                              SizedBox(width: 10),
                              Text(
                                'Tap to login with biometric',
                                style: TextStyle(
                                  color: Colors.white,
                                ),
                              ),
                            ],
                          ),
                        )
                            : Container(),
                      ],
                    ),
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
