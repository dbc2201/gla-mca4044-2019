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

```java
@Override
    protected void onStart() {
        super.onStart();
        Toast.makeText(LoginActivity.this, "onStart", Toast.LENGTH_LONG).show();
        Log.i("MainActivity:onStart", "onStart called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Toast.makeText(LoginActivity.this, "onResume", Toast.LENGTH_SHORT).show();
        Log.i("MainActivity:onResume", "onResume called");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Toast.makeText(LoginActivity.this, "onPause", Toast.LENGTH_SHORT).show();
        Log.i("MainActivity:onPause", "onPause called");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Toast.makeText(LoginActivity.this, "onStop", Toast.LENGTH_SHORT).show();
        Log.i("MainActivity:onStop", "onStop called");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Toast.makeText(LoginActivity.this, "onDestroy", Toast.LENGTH_SHORT).show();
        Log.i("MainActivity:onDestroy", "onDestroy called");
    }
```
___