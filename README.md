# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:



## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Deepika D
Registeration Number: 212225040059
*/

Activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:src="@mipmap/ic_launcher"
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:layout_marginBottom="20dp" />

    <Button
        android:id="@+id/blinkBtn"
        android:text="Blink Animation"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/rotateBtn"
        android:text="Rotate Animation"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/fadeBtn"
        android:text="Fade Animation"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/moveBtn"
        android:text="Move Animation"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/zoomBtn"
        android:text="Zoom Animation"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/stopBtn"
        android:text="Stop Animation"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp" />

</LinearLayout>



MainActivity.java


package com.example.animation;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import com.example.animation.R;

public class MainActivity extends AppCompatActivity {

    ImageView imageView;
    Button blinkBtn, rotateBtn, fadeBtn, moveBtn, zoomBtn, stopBtn;
    Animation animation;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);
        blinkBtn = findViewById(R.id.blinkBtn);
        rotateBtn = findViewById(R.id.rotateBtn);
        fadeBtn = findViewById(R.id.fadeBtn);
        moveBtn = findViewById(R.id.moveBtn);
        zoomBtn = findViewById(R.id.zoomBtn);
        stopBtn = findViewById(R.id.stopBtn);

        blinkBtn.setOnClickListener(v -> startAnim(R.anim.blink));
        rotateBtn.setOnClickListener(v -> startAnim(R.anim.rotate));
        fadeBtn.setOnClickListener(v -> startAnim(R.anim.fade));
        moveBtn.setOnClickListener(v -> startAnim(R.anim.move));
        zoomBtn.setOnClickListener(v -> startAnim(R.anim.zoom));

        stopBtn.setOnClickListener(v -> {
            if (animation != null) {
                imageView.clearAnimation(); // Stop animation
            }
        });
    }

    private void startAnim(int animRes) {
        animation = AnimationUtils.loadAnimation(getApplicationContext(), animRes);
        imageView.startAnimation(animation);
    }
}


AndroidManifest.xml



<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Animation">

        <!-- Add android:exported="true" -->
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>



Blink.xml


<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="0.0"
    android:toAlpha="1.0"
    android:duration="500"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />



Rotate.xml


<?xml version="1.0" encoding="utf-8"?>
<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatCount="infinite" />


Fade.xml


<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="2000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />



Move.xml


<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0"
    android:toXDelta="200"
    android:fromYDelta="0"
    android:toYDelta="200"
    android:duration="1500"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />



Zoom.xml


<?xml version="1.0" encoding="utf-8"?>
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="1.5"
    android:fromYScale="1.0"
    android:toYScale="1.5"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />




```

## OUTPUT

<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/93ea14f6-a6de-4d1c-8dc8-320da461d93a" />


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eb68abc2-d43c-4e76-9418-5c2215a87e0b" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/77eaadc8-5d71-4779-a097-b1f2103026ab" />


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d00a4524-9103-4c4c-85be-e732545c9d10" />



<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2a5dbdda-8dd9-426f-9bc2-1783306c5d88" />



<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/24705cd4-c57b-48b4-91c7-15abc2bab5d6" />






## RESULT



Thus,the experiment Implementation of Animation application using android studio executed successfully.

