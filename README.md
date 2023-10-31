# DeretBilanganFibonacci

Nama : Syifa Aurellia Rahma

NIM : 312210009

Kelas : TI.22.A1

Mata Kuliah : Pemrograman Mobile 1

Tugas : Buatlah Method Program java Toast Number, dengan menghasilkan Bilangan Fibonacci

## Code pada menu program java class `(MainActivity.java)` :
```
package com.example.fibonaccisequence;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    private int count = 1;
    private TextView showcount;
    private Button mbtnToast,mbtnCount, mbtnRestart;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_toast);

        showcount = findViewById(R.id.show_count);
        mbtnToast = findViewById(R.id.btnToast);
        mbtnCount = findViewById(R.id.btnCount);
        mbtnRestart = findViewById(R.id.btnRestart);

        mbtnToast.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                showToast();
            }
        });

        mbtnCount.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                countTop();
            }
        });
        mbtnRestart.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                count = 1;
                showcount.setText("1");
            }
        });
    }

    public void showToast() {
        Toast toast = Toast.makeText(this, "Bilangan Fibonacci", Toast.LENGTH_SHORT);
        toast.show();
    }
    public void countTop() {
        if (count < 0) {
            count = 0;
        }
        int result = generateFibonacci(count);
        showcount.setText(Integer.toString(result));
        count++;
    }

    private int generateFibonacci(int n) {
        if (n <= 0) {
            return 0;
        }
        else if (n == 1) {
            return 1;
        }

        int first = 1;
        int second = 1;

        for (int i = 2; i <= n; i++) {
            int next = first + second;
            first = second;
            second = next;
        }

        return second;
    }
}
```

## Code pada menu layout (activity_toast.xml) :
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:ignore="ExtraText"
    tools:context="com.example.fibonaccisequence.MainActivity">


    <Button
        android:id="@+id/btnToast"
        android:layout_width="406dp"
        android:layout_height="71dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="8dp"
        android:background="@color/colorPrimary"
        android:onClick="showToast"
        android:text="Toast"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="OnClick" />


    <Button
        android:id="@+id/btnCount"
        android:layout_width="181dp"
        android:layout_height="97dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="780dp"
        android:layout_marginEnd="8dp"
        android:background="@color/colorPrimary"
        android:onClick="countTop"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.034"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="OnClick" />

    <Button
        android:id="@+id/btnRestart"
        android:layout_width="192dp"
        android:layout_height="97dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="780dp"
        android:layout_marginEnd="8dp"
        android:background="@color/colorPrimary"
        android:onClick="Restart"
        android:text="Restart"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.963"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="OnClick" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="404dp"
        android:layout_height="658dp"
        android:layout_marginTop="8dp"
        android:background="#FFFF00"
        android:gravity="center_vertical"
        android:text="1"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/btnCount"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.513"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/btnToast"
        app:layout_constraintVertical_bias="0.272"
        tools:ignore="RtlCompat" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## Code pada menu values (strings.xml) :
```
<resources>
    <string name="app_name">FibonacciSequence</string>
    <string name="button_label_toast">Toast</string>
    <string name="button_label_count">Count</string>
    <string name="count_initial_value">1</string>
    <string name="toast_massage">Hello Toast!</string>
</resources>
```

## Code pada menu values (colors.xml) :
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="blue">#3700B3</color>
    <color name="pink">#FFC0CB</color>
    <color name="colorPrimary">#3F5185</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
</resources>
```


## Hasil run program bilangan Fibonacci :



https://github.com/syifaaurellia/DeretBilanganFibonacci/assets/115867244/3ee8d51d-dd1c-4397-8978-a72539bfced2






## Finish, Terima Kasih
