# TEDxVIT-by-manmohan-shrivastava
This repo holds the source code, apk, and instructional video used in creating the app.


Software and Websites Required = Android studio, Canva

Code:

acitivitymain.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:card_view="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <androidx.cardview.widget.CardView
        android:id="@+id/cardView"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="20dp"
        android:layout_marginEnd="20dp"
        android:layout_marginBottom="20dp"
        android:background="@drawable/custom_edittext"
        app:cardCornerRadius="30dp"
        app:cardElevation="40dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView3">


        <LinearLayout
            android:layout_width="352dp"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:orientation="vertical"
            android:padding="24dp">


            <TextView
                android:id="@+id/logintext"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="20dp"
                android:fontFamily="@font/alata"
                android:text="Welcome"
                android:textAlignment="textStart"
                android:textColor="@color/red"
                android:textSize="50sp"
                android:textStyle="normal" />

            <EditText
                android:id="@+id/username"
                android:layout_width="300dp"
                android:layout_height="50dp"
                android:layout_marginTop="20dp"
                android:background="@drawable/custom_edittext"
                android:drawableLeft="@drawable/baseline_person_24"
                android:drawablePadding="8dp"
                android:elevation="40dp"
                android:fontFamily="@font/alata"
                android:hint="Username"
                android:padding="8dp"
                android:textColor="@color/black"
                android:textColorHighlight="@color/cardview_dark_background" />

            <EditText
                android:id="@+id/password"
                android:layout_width="300dp"
                android:layout_height="50dp"
                android:layout_marginTop="20dp"
                android:background="@drawable/custom_edittext"
                android:drawableLeft="@drawable/baseline_lock_24"
                android:drawablePadding="8dp"
                android:elevation="50dp"
                android:fontFamily="@font/alata"
                android:hint="Password"
                android:inputType="textPassword"
                android:padding="8dp"
                android:textColor="@color/black"
                android:textColorHighlight="@color/cardview_dark_background" />

            <Button
                android:id="@+id/loginbutton"
                android:layout_width="300dp"
                android:layout_height="60dp"
                android:layout_marginTop="30dp"
                android:backgroundTint="@color/white"
                android:elevation="40dp"
                android:fontFamily="@font/alata"
                android:text="Login"
                android:textColor="@color/red"
                android:textSize="18sp"
                app:cornerRadius="20dp" />


        </LinearLayout>
    </androidx.cardview.widget.CardView>


    <ImageView
        android:id="@+id/imageView3"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="25dp"
        android:layout_marginTop="115dp"
        android:layout_marginEnd="25dp"
        android:layout_marginBottom="63dp"
        android:src="@drawable/black"
        app:layout_constraintBottom_toTopOf="@+id/cardView"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />


</androidx.constraintlayout.widget.ConstraintLayout>


activitymain.java


public class MainActivity extends AppCompatActivity {
    EditText username;
    EditText password;
    Button loginButton;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        username = findViewById(R.id.username);
        password = findViewById(R.id.password);
        loginButton = findViewById(R.id.loginbutton);

        loginButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                if (username.getText().toString().equals("admin") && password.getText().toString().equals("password")) {
                    Toast.makeText(MainActivity.this, "Login successful!", Toast.LENGTH_SHORT).show(); openActivity2();
                } else {
                    Toast.makeText(MainActivity.this, "login Failed, try again:(", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }
    public void openActivity2() {
        Intent intent = new Intent(this, Activity2.class);
        startActivity(intent);
    }
}

activity_2.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/hvjhv"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".Activity2">


    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginBottom="29dp"
        android:fontFamily="@font/alata"
        android:text="Welcome"
        android:textAlignment="textStart"
        android:textColor="@color/black"
        android:textSize="36sp"
        app:layout_constraintBottom_toTopOf="@+id/myfeed"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="87dp"
        android:layout_height="0dp"

        android:layout_marginStart="16dp"
        android:layout_marginTop="39dp"
        android:layout_marginBottom="30dp"
        android:src="@drawable/baseline_person_24"
        app:layout_constraintBottom_toTopOf="@+id/textView"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/myfeed"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginBottom="27dp"
        android:backgroundTint="@color/red"
        android:fontFamily="@font/alata"
        android:text="My feed"
        android:textAlignment="viewStart"
        android:textColor="@color/white"
        android:textSize="25sp"
        android:textStyle="bold"
        app:cornerRadius="20dp"
        app:layout_constraintBottom_toTopOf="@+id/myprofile"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />

    <Button
        android:id="@+id/myprofile"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginBottom="39dp"
        android:backgroundTint="@color/red"
        android:fontFamily="@font/alata"
        android:text="Profile"
        android:textColor="@color/white"
        android:textSize="25sp"
        android:textStyle="bold"
        app:cornerRadius="20dp"
        app:layout_constraintBottom_toTopOf="@+id/settings"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/myfeed" />

    <Button
        android:id="@+id/settings"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginBottom="243dp"
        android:backgroundTint="@color/red"
        android:fontFamily="@font/alata"
        android:text="Settings"
        android:textColor="@color/white"
        android:textSize="25sp"
        android:textStyle="bold"
        app:cornerRadius="20dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/myprofile" />

</androidx.constraintlayout.widget.ConstraintLayout>


activity_2.java

package com.example.ted;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class Activity2 extends AppCompatActivity {
    Button myfeed;
    Button myprofile;
    Button settings;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_2);

        myfeed = findViewById(R.id.myfeed);
        myprofile = findViewById(R.id.myprofile);
        settings = findViewById(R.id.settings);

        myfeed.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                openMainActivity4();
            }
        });

        myprofile.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(Activity2.this, "This Feature is work in progress, try again later", Toast.LENGTH_SHORT).show();
            }
        });

        settings.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(Activity2.this, "This Feature is work in progress, try again later", Toast.LENGTH_SHORT).show();
            }
        });


    }
    public void openMainActivity4() {
        Intent intent = new Intent(this, MainActivity4.class);
        startActivity(intent);
    }
}


activitymain4.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    android:orientation="vertical"
    tools:context=".MainActivity4">

    <TextView
        android:id="@+id/textView3"
        android:layout_width="206dp"
        android:layout_height="68dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="16dp"
        android:layout_marginBottom="56dp"
        android:background="@drawable/sus"
        android:fontFamily="@font/alata"
        android:gravity="center"
        android:text="Your Feed"
        android:textColor="@color/white"
        android:textSize="35sp"
        app:layout_constraintBottom_toTopOf="@+id/imageView2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="11dp"
        android:layout_marginEnd="11dp"
        android:fontFamily="sans-serif-black"
        android:gravity="center"
        android:text="TEDx is a grassroots initiative, created in the spirit of TED’s overall mission to research and discover “ideas worth spreading.” TEDx brings the spirit of TED to local communities around the globe through TEDx events. These events are organized by passionate individuals who seek to uncover new ideas and to share the latest research in their local areas that spark conversations in their communities. TEDx events include live speakers and recorded TED Talks, and are organized independently under a free license granted by TED."
        app:layout_constraintBottom_toTopOf="@+id/imageView4"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView2" />

    <ImageView
        android:id="@+id/imageView2"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="6dp"
        android:layout_marginEnd="6dp"
        android:layout_marginBottom="44dp"
        android:foregroundGravity="center"
        android:src="@drawable/duwebf"
        app:layout_constraintBottom_toTopOf="@+id/textView4"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView3" />

    <ImageView
        android:id="@+id/imageView4"
        android:layout_width="268dp"
        android:layout_height="186dp"
        android:layout_marginStart="60dp"
        android:layout_marginEnd="60dp"
        android:layout_marginBottom="5dp"
        android:src="@drawable/black"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView4" />


</androidx.constraintlayout.widget.ConstraintLayout>










