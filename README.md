
package com.example.simplecalculator;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private EditText editText1;
    private EditText editText2;
    private TextView textViewResult;
    private Button buttonAdd;
    private Button buttonSubtract;
    private Button buttonMultiply;
    private Button buttonDivide;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText1 = findViewById(R.id.editText1);
        editText2 = findViewById(R.id.editText2);
        textViewResult = findViewById(R.id.textViewResult);
        buttonAdd = findViewById(R.id.buttonAdd);
        buttonSubtract = findViewById(R.id.buttonSubtract);
        buttonMultiply = findViewById(R.id.buttonMultiply);
        buttonDivide = findViewById(R.id.buttonDivide);

        buttonAdd.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String num1Str = editText1.getText().toString();
                String num2Str = editText2.getText().toString();

                if (num1Str.isEmpty() || num2Str.isEmpty()) {
                    textViewResult.setText("Please enter both numbers.");
                    return;
                }

                double num1 = Double.parseDouble(num1Str);
                double num2 = Double.parseDouble(num2Str);
                double result = num1 + num2;

                textViewResult.setText(String.valueOf(result));
            }
        });

        buttonSubtract.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String num1Str = editText1.getText().toString();
                String num2Str = editText2.getText().toString();

                if (num1Str.isEmpty() || num2Str.isEmpty()) {
                    textViewResult.setText("Please enter both numbers.");
                    return;
                }

                double num1 = Double.parseDouble(num1Str);
                double num2 = Double.parseDouble(num2Str);
                double result = num1 - num2;

                textViewResult.setText(String.valueOf(result));
            }
        });

        buttonMultiply.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String num1Str = editText1.getText().toString();
                String num2Str = editText2.getText().toString();

                if (num1Str.isEmpty() || num2Str.isEmpty()) {
                    textViewResult.setText("Please enter both numbers.");
                    return;
                }

                double num1 = Double.parseDouble(num1Str);
                double num2 = Double.parseDouble(num2Str);
                double result = num1 * num2;

                textViewResult.setText(String.valueOf(result));
            }
        });

        buttonDivide.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String num1Str = editText1.getText().toString();
                String num2Str = editText2.getText().toString();

                if (num1Str.isEmpty() || num2Str.isEmpty()) {
                    textViewResult.setText("Please enter both numbers.");
                    return;
                }

                double num1 = Double.parseDouble(num1Str);
                double num2 = Double.parseDouble(num2Str);

                if (num2 == 0) {
                    textViewResult.setText("Cannot divide by zero.");
                    return;
                }

                double result = num1 / num2;

                textViewResult.setText(String.valueOf(result));
            }
        });
    }
}
