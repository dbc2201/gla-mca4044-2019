# Activity States and Life Cycles in Android

## MCA4044 - Mobile Application Development in Android, GLA University 2019

![android activity life cycle flowchart](https://developer.android.com/guide/components/images/activity_lifecycle.png)

___

There are basically the following states on any 'Activity' in Android -

1. [onCreate](https://developer.android.com/reference/android/app/Activity#onCreate(android.os.Bundle))  
2. [onStart](https://developer.android.com/reference/android/app/Activity#onStart(android.os.Bundle))  
3. onRestart: calls onStart() 
4. [onResume](https://developer.android.com/reference/android/app/Activity#onResume())  
5. [onPause](https://developer.android.com/reference/android/app/Activity#onPause())  
6. [onStop](https://developer.android.com/reference/android/app/Activity#onStop())  
7. [onDestroy](https://developer.android.com/reference/android/app/Activity#onDestroy())  

## Sample code for the activity callback methods

```javapublic class MainActivity extends AppCompatActivity {
       
           private static final String TAG = "MainActivity";
           
           @Override
           protected void onCreate(Bundle savedInstanceState) {
               super.onCreate(savedInstanceState);
               setContentView(R.layout.activity_main);
               Log.e("MainActivity:onCreate", "called");
           }
           
           @Override
           protected void onStart() {
               super.onStart();
               Toast.makeText(MainActivity.this, "onStart", Toast.LENGTH_SHORT).show();
               Log.e("MainActivity:onStart", "called");
           }
       
           @Override
           protected void onResume() {
               super.onResume();
               Toast.makeText(MainActivity.this, "onResume", Toast.LENGTH_SHORT).show();
               Log.e(TAG, "onResume: called");
           }
       
           @Override
           protected void onPause() {
               super.onPause();
               Toast.makeText(this, "onPause", Toast.LENGTH_SHORT).show();
               Log.e(TAG, "onPause: called");
           }
       
           @Override
           protected void onStop() {
               super.onStop();
               Toast.makeText(this, "onStop", Toast.LENGTH_SHORT).show();
               Log.e(TAG, "onStop: called");
           }
       
           @Override
           protected void onDestroy() {
               super.onDestroy();
               Toast.makeText(this, "onDestroy", Toast.LENGTH_SHORT).show();
               Log.e(TAG, "onDestroy: called");
           }
       }
```
___