# Android_Calculator
package com.example.personalitycheck;

import androidx.appcompat.app.AppCompatActivity;


import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;



public class MainActivity extends AppCompatActivity {

    Button equal,multiply,divide,subtract,ad,b0,b1,b2,b3,b4,b5,b6,b7,b8,b9,clear;
    TextView tv;
private String ss="0";////////////////////////////declare outside onbt function
    private int num_1 ;
   private int flag=0;
private int num_2,ans;





    public void onbt(View view){

        Toast.makeText(this, "done", Toast.LENGTH_SHORT).show();


        b0=findViewById(R.id.bt0);
        b1=findViewById(R.id.bt1);
        b2=findViewById(R.id.bt2);
        b3=findViewById(R.id.bt3);
        b4=findViewById(R.id.bt4);
        b5=findViewById(R.id.bt5);
        b6=findViewById(R.id.bt6);
        b7=findViewById(R.id.bt7);
        b8=findViewById(R.id.bt8);
        b9=findViewById(R.id.bt9);
        tv=findViewById(R.id.textView);
        ad=findViewById(R.id.plus);
        multiply=findViewById(R.id.mul);
        subtract=findViewById(R.id.sub);
        divide=findViewById(R.id.div);

        equal=findViewById(R.id.eq);




        switch(view.getId()) {
            case R.id.bt0:
                tv.append("0");
                //ss.concat("1");// does not work
                ss = ss + '0';
                break;

            case R.id.bt1:
                tv.append("1");
                ss = ss + '1';
                break;

            case R.id.bt2:
                tv.append("2");
                ss = ss + '2';
                break;

            case R.id.bt3:
                tv.append("3");
                ss = ss + '3';
                break;


            case R.id.bt4:
                tv.append("4");
                ss = ss + '4';
                break;

            case R.id.bt5:
                tv.append("5");
                ss = ss + '5';
                break;

            case R.id.bt6:
                tv.append("6");
                ss = ss + '6';
                break;

            case R.id.bt7:
                tv.append("7");
                ss = ss + '7';
                break;

            case R.id.bt8:
                tv.append("8");
                ss = ss + '8';
                break;

            case R.id.bt9:
                tv.append("9");
                ss = ss + '9';
                break;

            case R.id.plus:
                num_1 = Integer.parseInt(tv.getText().toString());
                flag = 1;
                tv.append("+");
                ss = "0";
                break;

            case R.id.mul:
                num_1 = Integer.parseInt(tv.getText().toString());
                flag = 2;
                tv.append("*");
                ss = "0";
                break;

            case R.id.div:
                num_1 = Integer.parseInt(tv.getText().toString());
                flag = 3;
                tv.append("%");
                ss = "0";
                break;

            case R.id.sub:
                num_1 = Integer.parseInt(tv.getText().toString());
                flag = 4;
                tv.append("-");
                ss = "0";
                break;


            default:tv.append("dh");
        }}

    public void onE(View view){

        num_2 = Integer.parseInt(ss);


switch(flag) {
    case 0:tv.append("dkjh");


    case 1://add

    ans = num_2 + num_1;

    tv.setText(Integer.toString(ans));
    ss = "0";
    break;
    case 2://mul
ans=num_1*num_2;

        tv.setText(Integer.toString(ans));
        ss = "0";
        break;
    case 3://div
ans=num_1/num_2;
        tv.setText(Integer.toString(ans));
        ss = "0";
    break;
    case 4://sub

        ans = num_1 - num_2;

        tv.setText(Integer.toString(ans));
        ss = "0";


    break;
    default:tv.append("bkj");

}

}

    public void onC(View view){
        tv=findViewById(R.id.textView);
        equal=findViewById(R.id.clr);
tv.setText("");
           tv.getCurrentHintTextColor();
          tv.setHint("answer");

    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {




        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);






    }
}
