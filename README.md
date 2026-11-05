EXPERIMENT 4 – UTILIZE THE ASSETS AND MEDIA
Aim
To add and display image, audio and video assets in a Flutter application.
Step 1
Create project:
flutter create media_app
cd media_app
Step 2 – Create asset directory
Inside the project:
media_app/
├── assets/
│ ├── images/
│ ├── audio/
│ └── video/
Step 3 – Add an image
Copy an image into:
assets/images/
For example:
assets/images/flutter.png
Step 4 – Modify pubspec.yaml
Add:
flutter:
assets:
- assets/images/
Be careful with YAML indentation.
Step 5 – Get packages
flutter pub get

Step 6 – Display image
Image.asset(
'assets/images/flutter.png',
)
Step 7 – Create image gallery
GridView.count(
crossAxisCount: 2,
children: [
Image.asset('assets/images/flutter.png'),
Image.asset('assets/images/flutter.png'),
],
)
Step 8 – Test
flutter run




Step 1 – Create Flutter project
Open VS Code → Terminal → New Terminal.

Run:
flutter create media_app
cd media_app
code .


Step 2 – Create asset folders
In VS Code Explorer, right-click the project folder → New Folder → create assets.

Inside assets, create:
assets/
├── images/
├── audio/
└── video/


Step 3 – Add Flutter image
Download a Flutter logo image and copy it into:
assets/images/flutter.png


Make sure the image filename is exactly flutter.png.









Step 4 – Modify pubspec.yaml
Open pubspec.yaml.

Find the existing flutter: section and modify it as follows:
flutter:
  uses-material-design: true

  assets:
    - assets/images/
    - assets/audio/
    - assets/video/


Important: Use two spaces before uses-material-design and assets, and four spaces before each asset path. Do not add a second flutter: section.
Step 5 – Install packages
In the terminal:
flutter pub get


Step 6 – Add complete code in main.dart
Open lib/main.dart, delete the existing code, and paste this:
Complete working code
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Media Application'),
          backgroundColor: Colors.blue,
        ),
        body: SingleChildScrollView(
          child: Column(
            children: [
              const SizedBox(height: 20),

              const Text(
                'Flutter Image',
                style: TextStyle(fontSize: 22),
              ),

              Image.asset(
                'assets/images/flutter.png',
                height: 150,
              ),

              const SizedBox(height: 20),

              const Text(
                'Image Gallery',
                style: TextStyle(fontSize: 22),
              ),

              GridView.count(
                crossAxisCount: 2,
                shrinkWrap: true,
                physics: const NeverScrollableScrollPhysics(),
                children: [
                  Image.asset('assets/images/flutter.png'),
                  Image.asset('assets/images/flutter.png'),
                ],
              ),

              const Text(
                'Media Assets Loaded Successfully!',
                style: TextStyle(color: Colors.green),
              ),
            ],
          ),
        ),
      ),
    );
  }
}


Step 7 – Run the application
Save using Ctrl + S.

Run:
flutter run -d chrome
Expected Result
The Flutter application successfully loads and displays the configured media
assets.
