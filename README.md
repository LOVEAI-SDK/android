# android
LOVEAI SDK for Android

It is highly recommended to use Android Studio to develop the application.

Download & unzip the SDK

Download the SDK

Make sure you have added the mylib-release.aar to your classpath

    dependencies {
        implementation files('libs/mylib-release.aar')
    }
    allprojects {
        repositories {
        flatDir{
        dirs 'libs'
        }
    }

Add the permission in your AndroidManifest.xml

	<uses-permission android:name="android.permission.INTERNET" />
	<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
	<uses-permission android:name="android.permission.BLUETOOTH" />
	<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
	<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
	<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

Register service(lib.loveai.com.mylib.BluetoothService) and activity(lib.loveai.com.mylib.DeviceScanActivity)

		 <service android:name="lib.loveai.com.mylib.BluetoothService"
							android:exported="true" >
		 </service>
		 <activity android:name="lib.loveai.com.mylib.DeviceScanActivity"
						android:theme="@style/my_theme"
						android:screenOrientation="portrait"/>
						
Connect to the LOVEAI toys

There are only 2 steps to use LOVEAI SDK:

        1. Open the Scan Activity to connect to LOVEAI Toys:
        Intent intent = new Intent(this, DeviceScanActivity.class);
        startActivity(intent);

        2. Send commands to the LOVEAI Toys:
        Intent intent = new Intent(RateUtils.ACTION_SEND);
        intent.putExtra("STR", RateUtils.POWER_OFF);
        sendBroadcast(intent);


COMMAND LIST

        RateUtils.RATE_01(RATE_20)  -- Vibrate the toy .The parameter must be between 01 and 20.
        RateUtils.STOP -- Stop vibrate the toy.
        RateUtils.GET_BATTERY -- Get battery status.
        RateUtils.POWER_OFF -- Turn off the toy.
        RateUtils.LIGHT_OFF -- Turn off the light.
        RateUtils.LIGHT_ON -- Turn on the light

 For more information, you can refer to the sample program.
 
 Products can be purchased from the following websites:
 
 https://www.amazon.com/dp/B0825RZNL
 
 https://item.taobao.com/item.htm?spm=a2oq0.12575281.0.0.25911debYCTzn5&ft=t&id=581407108602
