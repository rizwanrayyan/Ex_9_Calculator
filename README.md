# Ex.No:9 Develop a simple calculator using android studio.
## AIM:
To develop a program to develop a simple calculator in Android Studio.

## EQUIPMENTS REQUIRED:
Android Studio(Latest Version)

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Display the calculator operation in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
### MainActivity.java:
```
package com.example.ex8;

import androidx.appcompat.app.AppCompatActivity;
//import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
import android.os.Bundle;
import android.os.Bundle;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText e1, e2;
    TextView t1;
    int num1, num2;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public boolean getNumbers() {

        e1 = (EditText) findViewById(R.id.num1);

        e2 = (EditText) findViewById(R.id.num2);

        t1 = (TextView) findViewById(R.id.result);

        String s1 = e1.getText().toString();

        String s2 = e2.getText().toString();

        if ((s1.equals(null) && s2.equals(null))
                || (s1.equals("") && s2.equals(""))) {

            String result = "Please enter a value";
            t1.setText(result);

            return false;
        } else {
            num1 = Integer.parseInt(s1);

            num2 = Integer.parseInt(s2);
        }

        return true;
    }

    public void doSum(View v) {

        if (getNumbers()) {
            int sum = num1 + num2;
            t1.setText(num1+"+"+num2+"="+Integer.toString(sum));
        }
    }

    public void doSub(View v) {

        if (getNumbers()) {
            int sub = num1 - num2;
            t1.setText(num1+"-"+num2+"="+Integer.toString(sub));
        }
    }

    public void doMul(View v) {

        if (getNumbers()) {
            int mul = num1 * num2;
            t1.setText(num1+"*"+num2+"="+Integer.toString(mul));
        }
    }

    public void doDiv(View v) {

        if (getNumbers()) {

            double div = num1 / (num2 * 1.0);
            t1.setText(num1 + "/" + num2 + "=" + Double.toString(div));
        }
    }
}
```
### Activity_Main.XML:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#000000"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="194dp"
        android:layout_height="43dp"
        android:layout_marginStart="114dp"
        android:layout_marginLeft="114dp"
        android:layout_marginTop="58dp"
        android:layout_marginEnd="103dp"
        android:layout_marginRight="103dp"
        android:layout_marginBottom="502dp"
        android:scrollbarSize="30dp"
        android:text=" Calculator"
        android:textAlignment="center"
        android:textStyle="bold"
        android:background="#000000"
        android:textColor="#FF1200"
        android:textAppearance="@style/TextAppearance.AppCompat.Body1"
        android:textSize="30dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/num1"
        android:layout_width="364dp"
        android:layout_height="28dp"
        android:layout_marginStart="72dp"
        android:layout_marginTop="70dp"
        android:layout_marginEnd="71dp"
        android:layout_marginBottom="416dp"
        android:background="#000000"
        android:textColor="#FF1200"
        android:ems="10"
        android:hint="Number 1"
        android:textStyle="bold"
        android:textColorHint="#FF1200"
        android:inputType="number"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/num2"
        android:layout_width="363dp"
        android:layout_height="30dp"
        android:layout_marginStart="72dp"
        android:layout_marginTop="112dp"
        android:layout_marginEnd="71dp"
        android:layout_marginBottom="374dp"
        android:background="#000000"
        android:textColor="#FF1200"
        android:ems="10"
        android:hint="Number 2"
        android:textStyle="bold"
        android:textColorHint="#FF1200"
        android:inputType="number"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/result"
        android:layout_width="356dp"
        android:layout_height="71dp"
        android:layout_marginStart="41dp"
        android:layout_marginTop="151dp"
        android:layout_marginEnd="48dp"
        android:layout_marginBottom="287dp"
        android:background="#000000"
        android:textColor="#FF1200"
        android:text="Result"
        android:textStyle="bold"
        android:textColorLink="#673AB7"
        android:textSize="25sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/sum"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="307dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="#FF1200"
        android:onClick="doSum"
        android:text="+"
        android:textSize="70px"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/sub"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="210dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="113dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="#FF1200"
        android:onClick="doSub"
        android:text="-"
        android:textSize="70px"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/div"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="307dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="16dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="#FF1200"
        android:onClick="doDiv"
        android:text="/"
        android:textSize="70px"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/mul"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="113dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="210dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="#FF1200"
        android:onClick="doMul"
        android:text="x"
        android:textSize="70px"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />


</androidx.constraintlayout.widget.ConstraintLayout>
```
## OUTPUT

![Screenshot 2024-10-17 132400](https://github.com/user-attachments/assets/fdae2b08-84d2-4bad-8f7a-ab4a5e58faeb)


## RESULT
Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.
