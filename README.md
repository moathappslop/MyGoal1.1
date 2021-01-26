# MyGoal1.1
My Goal App

Update My Goal App

#MainActivity
package com.moath.mygoal

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.Toast



class MainActivity : AppCompatActivity() {

    // region Setup Methods

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val zipcodeEditText: EditText = findViewById(R.id.zipcodeEditText)
        val enterbutton: Button = findViewById(R.id.enterbutton)

        enterbutton.setOnClickListener {
            val zipcode: String = zipcodeEditText.text.toString()

            if (zipcode.length != 5) {
                Toast.makeText(this, R.string.zipcode_entry_error, Toast.LENGTH_SHORT).show()
            } else {
                Toast.makeText(this, zipcode, Toast.LENGTH_SHORT).show()
            }

        }
    }


    override fun onStart() {
        super.onStart()
    }

    override fun onResume() {
        super.onResume()
    }

    // endregion Setup Methods

    // region Teardown Methods


    override fun onPause() {
        super.onPause()
    }

    override fun onStop() {
        super.onStop()
    }

    override fun onDestroy() {
        super.onDestroy()
    }

    // endregion Teardown Methods
}


#activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">


    <ImageView
        android:id="@+id/icon"
        android:layout_width="@dimen/zipcode_entry_icon_size"
        android:layout_height="@dimen/zipcode_entry_icon_size"

        android:layout_marginBottom="72dp"
        android:contentDescription="@string/todo"
        android:src="@drawable/ic_baseline_android_24"
        app:layout_constraintBottom_toTopOf="@+id/title"
        app:layout_constraintEnd_toEndOf="@+id/title"
        app:layout_constraintHorizontal_bias="0.427"
        app:layout_constraintStart_toStartOf="@+id/enterbutton" />

    <TextView
        android:id="@+id/title"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="52dp"
        android:text="@string/enter_your_zipcode"
        android:textSize="21sp"
        app:layout_constraintBottom_toTopOf="@+id/zipcodeEditText"
        app:layout_constraintEnd_toEndOf="@+id/zipcodeEditText"
        app:layout_constraintHorizontal_bias="0.491"
        app:layout_constraintStart_toStartOf="@+id/zipcodeEditText" />

    <EditText
        android:id="@+id/zipcodeEditText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="18dp"
        android:autofillHints=""
        android:hint="@string/enter_zipcode"
        android:inputType="number"
        app:layout_constraintBottom_toTopOf="@+id/enterbutton"
        app:layout_constraintEnd_toEndOf="@+id/enterbutton"
        app:layout_constraintHorizontal_bias="0.421"
        app:layout_constraintStart_toStartOf="@+id/enterbutton"
        tools:layout_editor_absolutex="137dp" />

    <Button
        android:id="@+id/enterbutton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/submit_zipcode"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
