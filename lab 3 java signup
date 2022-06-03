package com.varshith.haiihdhdhd;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;

import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import java.util.regex.*;

public class MainActivity extends AppCompatActivity {
    Button sign;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        String regex = "^(?=.*[0-9])"
                + "(?=.*[a-z])(?=.*[A-Z])"
                + "(?=.*[@#$%^&+=])"
                + "(?=\\S+$).{8,20}$";
        Pattern p = Pattern.compile(regex);
        EditText uname = (EditText)findViewById(R.id.username);
        EditText pass = (EditText)findViewById(R.id.password);
        sign = (Button) findViewById(R.id.signup);
        sign.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String username = uname.getText().toString();
                String password = pass.getText().toString();
                Matcher m = p.matcher(password);
                if(uname.length()==0 || password.length()==0){
                    Toast.makeText(getApplicationContext(),"Username or Password cannot is empty", Toast.LENGTH_SHORT).show();
                }
                else {
                    if(m.matches()== true) {
                        Intent intent = new Intent(MainActivity.this, Login.class);
                        Bundle extras = new Bundle();
                        extras.putString("EXTRA_USERNAME", username);
                        extras.putString("EXTRA_PASSWORD", password);
                        intent.putExtras(extras);
                        startActivity(intent);
                    }
                    else{
                        Toast.makeText(getApplicationContext(),"Password Pattern not matched", Toast.LENGTH_SHORT).show();
                    }
                }
            }
        });
    }
}
