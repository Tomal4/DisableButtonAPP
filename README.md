package com.example.buttondisableapp;


import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;


public class MainActivity
        extends AppCompatActivity {
    private Button buttonDisable;
    private Button buttonEnable;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        buttonDisable = findViewById(R.id.buttonDisable);
        buttonEnable = findViewById(R.id.buttonEnable);
        buttonEnable.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                buttonDisable.setEnabled(true);
                Toast.makeText( MainActivity.this, "Przycisk został wyłączony", Toast.LENGTH_SHORT).show();
                ;}
        });
         buttonDisable.setOnClickListener(new View.OnClickListener(){
             @Override
             public void onClick(View v)
             { buttonDisable.setEnabled(false);
             }
         });
    }
}



<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="16dp">

    <Button android:id="@+id/buttonDisable"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Kliknij mnie"
        android:textSize="18sp"/>

    <Button android:id="@+id/buttonEnable"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Reset"
        android:textSize="14sp"/>

</LinearLayout>
