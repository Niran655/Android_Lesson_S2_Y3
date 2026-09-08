# Chapter 4: Activity and Activity Life Cycle
## ផ្នែកទី ១៖ ខ្លឹមសារមេរៀនលម្អិត (Lesson Contents)

### ១. និយមន័យនៃ Activity
*   **Activity:** គឺជាសមាសធាតុដែលបង្ហាញផ្ទាំងផ្ទៃកម្មវិធី (**Visual User Interface ឬ Screen**) ទៅកាន់អ្នកប្រើប្រាស់ ដែលអនុញ្ញាតឱ្យពួកគាត់អាចធ្វើអន្តរកម្ម ឬសកម្មភាពផ្សេងៗនៅលើនោះបាន។ កម្មវិធី Android មួយអាចមាន Activities ច្រើនខុសៗគ្នា ហើយពួកវាត្រូវបានភ្ជាប់គ្នាទៅវិញទៅមក។

### ២. វដ្តជីវិតរបស់ Activity (Activity Lifecycle)
ដើម្បីគ្រប់គ្រងការផ្លាស់ប្តូររវាងដំណាក់កាលនីមួយៗនៃជីវិតរបស់ Activity, ប្រព័ន្ធ Android បានផ្តល់នូវ Callback Methods សំខាន់ៗចំនួន ៦ (បូករួមទាំងវិធីសាស្ត្រជំនួយ)៖
*   **`onCreate()`**: ត្រូវបានហៅឡើងមុនគេបង្អស់នៅពេល Activity ត្រូវបានបង្កើតឡើងជាលើកដំបូង។ វាជាកន្លែងសម្រាប់រៀបចំការដំឡើងដំបូង (ដូចជា `setContentView`)។
*   **`onStart()`**: ត្រូវបានហៅឡើងនៅពេល Activity ចាប់ផ្តើមបង្ហាញឱ្យអ្នកប្រើប្រាស់មើលឃើញ (Visible to the user)។
*   **`onResume()`**: ត្រូវបានហៅឡើងនៅពេល Activity ចាប់ផ្តើមដំណើរការនៅផ្ទៃខាងមុខបង្អស់ (**Foreground**) និងជាចំណុចដែលអ្នកប្រើប្រាស់អាចចាប់ផ្តើមធ្វើសកម្មភាពបញ្ជាបាន។
*   **`onPause()`**: ត្រូវបានហៅឡើងនៅពេល Activity បាត់បង់ការផ្ដោតអារម្មណ៍ (**Lost focus**) ប៉ុន្តែនៅតែអាចមើលឃើញដោយផ្នែក (ឧទាហរណ៍៖ មាន Activity ផ្សេងដែលថ្លា ឬមិនពេញអេក្រង់មកបាំងពីលើ)។
*   **`onStop()`**: ត្រូវបានហៅឡើងនៅពេល Activity ត្រូវបានបាំងទាំងស្រុងដោយ Activity ផ្សេងទៀត និងលែងមើលឃើញដោយអ្នកប្រើប្រាស់។
*   **`onDestroy()`**: ត្រូវបានហៅឡើងមុនពេល Activity ត្រូវបានបំផ្លាញ ឬបិទចោលទាំងស្រុងពីប្រព័ន្ធដំណើរការ (System or finish)း។
*   **`onRestart()`**: ត្រូវបានហៅឡើងនៅពេល Activity ត្រូវបានចាប់ផ្តើមឡើងវិញ បន្ទាប់ពីវាត្រូវបាន Stopped។

### ៣. ស្ថានភាពរបស់ Activity (Activity States)
ផ្អែកលើដ្យាក្រាម **`android_activity_lifecycle_diagram.png`** ស្ថានភាពរបស់ Activity ត្រូវបានបែងចែកជា៖
*   **Active or Running:** កាលណាវាស្ថិតនៅផ្ទៃខាងមុខបង្អស់នៃអេក្រង់ (Foreground of the screen / Top of the activity stack) និងជាចំណុចផ្ដោតសម្រាប់ការធ្វើសកម្មភាពរបស់អ្នកប្រើប្រាស់។
*   **Paused:** កាលណាវាបាត់បង់ការ Focus ប៉ុន្តែនៅតែមើលឃើញ។ វានៅតែមានជីវិតពេញលេញនៅក្នុង Memory (រាល់ state និងព័ត៌មានសមាជិកទាំងអស់នៅរក្សាដដែល) ប៉ុន្តែអាចនឹងត្រូវប្រព័ន្ធសម្លាប់ចោល (Killed) ក្នុងករណីដែលឧបករណ៍ខ្វះខាត Memory ខ្លាំង។
*   **Stopped:** កាលណាវាត្រូវបានបាំងទាំងស្រុងដោយ Activity ផ្សេងទៀត។ វានៅតែរក្សា State និងព័ត៌មានដដែល ប៉ុន្តែបង្អួចរបស់វាត្រូវបានលាក់បាំង ហើយវានឹងត្រូវប្រព័ន្ធសម្លាប់ចោលជាញឹកញាប់នៅពេលត្រូវការ Memory។

### ៤. និយមន័យ និងប្រភេទនៃ Intent
*   **Intent:** គឺជា **Messaging Object** មួយដែលត្រូវបានប្រើប្រាស់ដើម្បីស្នើសុំឱ្យធ្វើសកម្មភាពណាមួយពីរន្ធសមាសធាតុផ្សេងៗ។ វាប្រើសម្រាប់៖
    *   ចាប់ផ្តើមដំណើរការ Activities, Services, និង Broadcasts។
    *   បញ្ជូនទិន្នន័យ (Data) រវាង Activities ឬសមាសធាតុផ្សំផ្សេងៗគ្នានៃកម្មវិធី។
*   **ប្រភេទរបស់ Intent៖**
    1.  **Explicit Intent (ច្បាស់លាស់):** ប្រើសម្រាប់បញ្ជាក់ចំឈ្មោះសមាសភាគ (Target Class) ដែលត្រូវហៅឱ្យដំណើរការដោយផ្ទាល់ ដោយអ្នកសរសេរកម្មវិធី។ ជាទូទៅប្រើដើម្បីបើកអេក្រង់បន្ទាប់ក្នុងកម្មវិធីខ្លួនឯង។
    2.  **Implicit Intent (មិនច្បាស់លាស់):** មិនបញ្ជាក់ឈ្មោះសមាសភាគចំៗនោះទេ។ វាផ្តល់ព័ត៌មានអំពីសកម្មភាពដែលចង់ធ្វើ (Action) ដើម្បីឱ្យប្រព័ន្ធ Android រកមើលកម្មវិធីផ្សេងៗនៅក្នុងទូរស័ព្ទមកជួយដោះស្រាយ (ដូចជា បើកទំព័រ web, ខលទូរស័ព្ទ, បើកម៉ាស៊ីនថតរូប)។

### ៥. ការបញ្ជូនទិន្នន័យរវាង Activities (Data Transfer)
យើងអាចបញ្ជូនទិន្នន័យពី Activity មួយទៅកាន់ Activity មួយទៀតបានតាមរយៈ Intent ដោយប្រើវិធីពីរយ៉ាង៖
*   **Bundle:** បង្កើត Object `Bundle` ដើម្បីផ្ទុកទិន្នន័យជាគូ `Key/Value` (ដោយ Key ជា String) រួចផ្ញើតាមរយៈ `putExtras()`។
*   **putExtra()**: ដាក់ទិន្នន័យចូលទៅក្នុង Intent ដោយផ្ទាល់ជាគូ `Key/Value` តាមរយៈ Method `putExtra()`។
*   **ប្រភេទតម្លៃដែលអាចផ្ញើបាន:** ប្រភេទ Primitive data types (int, float, ...) រួមទាំងប្រភេទ Objects ដូចជា String, Bundle, Parcelable និង Serializable។
*   **ការទទួលទិន្នន័យ (Get Data):** នៅអេក្រង់ទទួល យើងទាញយក Intent តាមរយៈ `getIntent()` រួចប្រើប្រាស់ Method `getAction()`, `getData()` ឬ `getIntent().getExtras()` ដើម្បីទទួលបានទិន្នន័យមកវិញ។

### ៦. Intent Filter
*   **Intent Filter:** គឺជាកន្សោមប្រកាស (Expression) នៅក្នុងឯកសារ **`AndroidManifest.xml`** របស់កម្មវិធី ដែលបញ្ជាក់ពីប្រភេទនៃ Intents ដែលសមាសធាតុនោះ (ដូចជា Activity) ចង់ទទួល។ វាប្រើប្រាស់ Element `<intent-filter>` ដើម្បីរាយបញ្ជីសកម្មភាព (actions), ប្រភេទ (categories), និងប្រភេទឯកសារទិន្នន័យ (data types)។

---

## ផ្នែកទី ២៖ កូដគំរូសំខាន់ៗ (Key Code Snippets)

### ១. កូដគំរូសម្រាប់តាមដានវដ្តជីវិត Activity (Java)
```java
public class MainActivity extends AppCompatActivity {
    private static final String TAG = MainActivity.class.getSimpleName();

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Log.d(TAG, "onCreated"); // ហៅពេលបង្កើតដំបូង
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d(TAG, "onStart"); // ហៅពេលចាប់ផ្តើមបង្ហាញ
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d(TAG, "onResume"); // ហៅពេលត្រៀមដំណើរការនៅមុខអេក្រង់
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d(TAG, "onPause"); // ហៅពេលបាត់បង់ការ Focus
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d(TAG, "onStop"); // ហៅពេលត្រូវបាំងទាំងស្រុង
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d(TAG, "onDestroy"); // ហៅពេលបំផ្លាញចោល
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        Log.d(TAG, "onRestart"); // ហៅពេលបើកឡើងវិញក្រោយពេល Stop
    }
}
```

### ២. Explicit Intent - បើកអេក្រង់ថ្មី (Java)
```java
// ការហៅបើកអេក្រង់ពី MainActivity ទៅកាន់ ActivityTwo ដោយមិនរំពឹងលទ្ធផលត្រឡប់
Intent intent = new Intent(MainActivity.this, ActivityTwo.class);
startActivity(intent);
```

### ៣. Implicit Intent - កូដគំរូប្រើប្រាស់ទូទៅ
*   **បើកមើលគេហទំព័រ (Way 1):**
    ```java
    Intent intent = new Intent();
    intent.setAction(Intent.ACTION_VIEW);
    intent.setData(Uri.parse("http://www.tutorialpoint.com"));
    startActivity(intent);
    ```
*   **បើកមើលគេហទំព័រ (Way 2):**
    ```java
    Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("http://www.tutorialpoint.com"));
    startActivity(intent);
    ```
*   **ធ្វើការហៅទូរស័ព្ទ (Phone Call):**
    ```java
    String uriString = "tel:" + "086-673-2111";
    Intent intent = new Intent(Intent.ACTION_DIAL); // ឬប្រើ ACTION_CALL (ត្រូវការ permission)
    intent.setData(Uri.parse(uriString));
    startActivity(intent);
    ```
*   **ផ្ញើសារ SMS:**
    ```java
    String uriString = "smsto:" + "0866732111";
    Intent intent = new Intent(Intent.ACTION_SENDTO);
    intent.setData(Uri.parse(uriString));
    intent.putExtra("sms_body", "The SMS text");
    startActivity(intent);
    ```
*   **ផ្ញើ Email:**
    ```java
    Intent intent = new Intent(Intent.ACTION_SEND);
    String aEmailList[] = { "eakkattiya@gmail.com", "eak.k@ibluecode.com" };
    intent.putExtra(Intent.EXTRA_EMAIL, aEmailList);
    intent.putExtra(Intent.EXTRA_SUBJECT, "My subject");
    intent.setType("plain/text");
    intent.putExtra(Intent.EXTRA_TEXT, "My message body.");
    startActivity(Intent.createChooser(intent, "Send your email with:"));
    ```
*   **ថតរូបភាព (Take a Photo):**
    ```java
    Intent intent = new Intent(android.provider.MediaStore.ACTION_IMAGE_CAPTURE);
    startActivityForResult(Intent.createChooser(intent, "Take a with:"), MY_CAMERA_REQUEST);
    ```

### ៤. ការផ្ញើ និងទទួលទិន្នន័យ (Data Passing)
*   **កូដខាងអេក្រង់ផ្ញើ (MainActivity - ប្រើ Bundle)៖**
    ```java
    Bundle mBundle = new Bundle();
    mBundle.putString("name", "Sokngim");
    mBundle.putInt("age", 24);

    Intent testingIntent = new Intent(MainActivity.this, TestingActivity.class);
    testingIntent.putExtras(mBundle);  // ដាក់ bundle ចូលទៅក្នុង intent
    startActivity(testingIntent);
    ```
*   **កូដខាងអេក្រង់ផ្ញើ (MainActivity - ប្រើ putExtra ផ្ទាល់)៖**
    ```java
    Intent testingIntent = new Intent(MainActivity.this, TestingActivity.class);
    testingIntent.putExtra("name", "Sokngim");
    testingIntent.putExtra("age", 24);
    startActivity(testingIntent);
    ```
*   **កូដខាងអេក្រង់ទទួល (TestingActivity)៖**
    ```java
    Bundle extras = getIntent().getExtras();
    if (extras != null) {
        String name = extras.getString("name");
        int age = extras.getInt("age", 0);
        Log.d("mBundle", "Name: " + name);
        Log.d("mBundle", "Age: " + age);
    }
    ```

### ៥. Intent Filter នៅក្នុង AndroidManifest.xml
```xml
<activity android:name=".MainActivity"
          android:label="@string/app_name">
    <intent-filter>
        <action android:name="com.example.My Application.LAUNCH" />
        <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
</activity>
```

---

## ផ្នែកទី ៣៖ កម្រងសំណួរសម្រាប់ប្រឡង (Exam Questions)

## ប្រភេទទី ១៖ សំណួរជ្រើសរើសចម្លើយ (Multiple Choice Questions)

**សំណួរ ១៖ តើអ្វីទៅជាការកំណត់និយមន័យនៃ "Activity" នៅក្នុងប្រព័ន្ធ Android?**
A. សមាសធាតុដំណើរការនៅខាងក្រោយដោយគ្មានការបង្ហាញផ្ទាំងអេក្រង់  
B. សមាសធាតុដែលបង្ហាញផ្ទាំងរូបរាង UI (Screen) សម្រាប់ធ្វើអន្តរកម្មជាមួយអ្នកប្រើប្រាស់  
C. សំណុំកូដសម្រាប់បញ្ជូនទិន្នន័យរវាងកម្មវិធីពីរ  
D. ប្រព័ន្ធមូលដ្ឋានទិន្នន័យផ្ទុកទិន្នន័យឯកជន  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 2៖ "Activity បង្ហាញ Visual User Interface (Screen) ដែលអ្នកប្រើប្រាស់ធ្វើសកម្មភាពលើវា...")។

**សំណួរ ២៖ តើក្នុងចំណោម Callback Methods ខាងក្រោមនេះ មួយណាជា Callback Method ដំបូងគេដែលត្រូវបានហៅនៅពេល Activity ចាប់ផ្តើមបង្កើតឡើង?**
A. `onStart()`  
B. `onResume()`  
C. `onCreate()`  
D. `onRestart()`  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 2 & 4៖ វដ្តជីវិតចាប់ផ្តើមពី `onCreate()`)។

**សំណួរ ៣៖ នៅពេលដែល Activity មួយលែងស្ថិតនៅលើកំពូលនៃអេក្រង់ (Lost Focus) ប៉ុន្តែនៅតែអាចមើលឃើញដោយផ្នែក តើស្ថានភាព (State) របស់វាស្ថិតក្នុងស្ថានភាពអ្វី?**
A. Active / Running  
B. Paused  
C. Stopped  
D. Destroyed  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 3៖ "Pause: If it has lost focus but is still visible to the user...")។

**សំណួរ ៤៖ តើមានអ្វីកើតឡើងចំពោះ Activity នៅក្នុងស្ថានភាព "Stopped State"?**
A. វានៅតែមើលឃើញដោយអ្នកប្រើប្រាស់  
B. បង្អួចរបស់វាត្រូវបានលាក់បាំងទាំងស្រុង ប៉ុន្តែវានៅតែរក្សាទុកព័ត៌មាន state និងសមាជិកដដែល  
C. វាត្រូវបានសម្លាប់ភ្លាមៗដោយគ្មានលក្ខខណ្ឌ  
D. វាមិនរក្សាទុកព័ត៌មាន state នោះទេ  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 4៖ "Stop: ... no longer visible to the user so its window is hidden, It still retains all state and member information.")។

**សំណួរ ៥៖ តើ Method មួយណាដែលត្រូវបានប្រើប្រាស់ដើម្បីចាប់ផ្តើម Activity មួយដោយរំពឹងនឹងទទួលបានលទ្ធផលត្រឡប់មកវិញ (Expect a result back)?**
A. `startActivity(Intent intent)`  
B. `startActivityForResult(Intent intent)`  
C. `startActivityWithResult(Intent intent)`  
D. `launchActivity(Intent intent)`  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 8៖ "startActivityForResult(Intent intent)៖ ជា Method សម្រាប់ចាប់ផ្តើម Activity ដោយរំពឹងនូវលទ្ធផលត្រលប់មកវិញ។")។

**សំណួរ ៦៖ ប្រសិនបើលោកអ្នកចង់បើកគេហទំព័រ ឬសេវាកម្មទូរស័ព្ទដែលមានស្រាប់នៅក្នុងប្រព័ន្ធ Android (System Apps) តើប្រភេទ Intent មួយណាដែលស័ក្តិសមបំផុត?**
A. Explicit Intent  
B. Implicit Intent  
C. Internal Intent  
D. Direct Intent  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 7៖ "Implicit Intent មិនបញ្ជាក់សមាសភាគទេ។ វាផ្តល់ព័ត៌មានអំពីសមាសធាតុដែលផ្តល់ដោយ system...")។

**សំណួរ ៧៖ តើពាក្យគន្លឹះ (Key) សម្រាប់ការបញ្ជូនទិន្នន័យ (Data Passing) រវាង Activities តាមរយៈ Intent ត្រូវតែមានប្រភេទជាអ្វីជានិច្ច?**
A. Integer  
B. Boolean  
C. String  
D. Object  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 9៖ "The key is always of type String.")។

**សំណួរ ៨៖ តើការកំណត់កំណត់បង្ហាញនៅក្នុង Manifest នៃប្រភេទ Intents ដែលសមាសធាតុនោះចង់ទទួលហៅថាអ្វី?**
A. Intent Filter  
B. Intent Action  
C. Intent Category  
D. Intent Permission  
*   **ចម្លើយត្រឹមត្រូវ៖ A** (យោងតាមស្លាយទី 12៖ "An intent filter is an expression in an app's manifest file that specifies the type of intents...")។

**សំណួរ ៩៖ នៅពេលអ្នកប្រើប្រាស់សង្កត់ប៊ូតុង "Back Button" នៅពេលកំពុងដំណើរការ Activity តើ Callback Method ណាមួយនឹងត្រូវហៅបន្ទាប់ពី `onStop()`?**
A. `onRestart()`  
B. `onDestroy()`  
C. `onCreate()`  
D. `onResume()`  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមលំដាប់លំដោយ និងដ្យាក្រាម lifecycle នៅពេលចុច Back គឺ Activity នឹងត្រូវបានបិទ និងបំផ្លាញចោល)។

**សំណួរ ១០៖ តើការទទួលទិន្នន័យ (Get Data) ដែលផ្ញើពី Bundle ក្នុង Activity ថ្មី អាចធ្វើឡើងតាមរយៈ Method ណាមួយនៃ Intent object?**
A. `getIntent().getBundle()`  
B. `getIntent().getExtras()`  
C. `getIntent().getData()`  
D. `getIntent().getString()`  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 11៖ "This Intent object can be retrieved via the getIntent() method... getIntent().getExtras();")។

---

## ប្រភេទទី ២៖ សំណួរសរសេរ និងដោះស្រាយកូដ (Structured & Coding Questions)

**សំណួរ ១៖** ចូរពន្យល់ពីលំដាប់នៃការហៅ Callback Methods របស់ Activity (Lifecycle Methods sequence) ផ្អែកលើដ្យាក្រាម `android_activity_lifecycle_diagram.png` នៅពេលដែលកម្មវិធីត្រូវបានបើកដំបូង រហូតដល់វាបង្ហាញនៅលើអេក្រង់ និងត្រៀមអន្តរកម្ម។
*   **ចម្លើយ៖** នៅពេលដែលកម្មវិធីត្រូវបានបើកជាលើកដំបូង លំដាប់នៃការដំណើរការគឺ៖
    1.  `onCreate()`: បង្កើត និងដំឡើង UI ប្លង់អេក្រង់។
    2.  `onStart()`: ចាប់ផ្តើមបង្ហាញផ្ទាំង UI ឱ្យអ្នកប្រើប្រាស់មើលឃើញ។
    3.  `onResume()`: Activity ចាប់ផ្តើមដំណើរការនៅផ្ទៃខាងមុខ និងត្រៀមទទួលការបញ្ជាពីអ្នកប្រើប្រាស់។

**សំណួរ ២៖** ចូរសរសេរកូដ Java សម្រាប់ការផ្ញើទិន្នន័យចំនួនពីរគឺ `Subject` (តម្លៃ: `"Android Study"`) និង `Code` (តម្លៃ: `404`) ពី `FirstActivity` ទៅកាន់ `SecondActivity` ដោយផ្ទាល់តាមរយៈវិធីសាស្ត្រ `putExtra()` នៃ `Intent`។
*   **ចម្លើយ៖**
    ```java
    Intent intent = new Intent(FirstActivity.this, SecondActivity.class);
    intent.putExtra("Subject", "Android Study");
    intent.putExtra("Code", 404);
    startActivity(intent);
    ```

**សំណួរ ៣៖** ចូរសរសេរកូដ Java ដើម្បីទទួលទិន្នន័យពីរដែលបានផ្ញើមកពីសំណួរទី ២ ខាងលើ នៅក្នុង `SecondActivity` និងបង្ហាញវាទៅក្នុង Logcat។
*   **ចម្លើយ៖**
    ```java
    Bundle extras = getIntent().getExtras();
    if (extras != null) {
        String subject = extras.getString("Subject");
        int code = extras.getInt("Code", 0);
        Log.d("SecondActivity", "Subject: " + subject + ", Code: " + code);
    }
    ```

**សំណួរ ៤៖** ចូរសរសេរកូដ XML សម្រាប់ប្រកាសនៅក្នុង `AndroidManifest.xml` ដើម្បីកំណត់ឱ្យ Activity ឈ្មោះ `DetailActivity` អាចគាំទ្រដំណើរការ Intent Action ប្រភេទ `ACTION_VIEW` និង Category `DEFAULT`។
*   **ចម្លើយ៖**
    ```xml
    <activity android:name=".DetailActivity">
        <intent-filter>
            <action android:name="android.intent.action.VIEW" />
            <category android:name="android.intent.category.DEFAULT" />
        </intent-filter>
    </activity>
    ```

**សំណួរ ៥៖** ចូរសរសេរកូដ Java ដើម្បីបង្កើតការផ្ញើសារ SMS ទៅកាន់លេខទូរស័ព្ទ `"099888777"` ដោយភ្ជាប់ជាមួយអត្ថបទខ្លឹមសារសារថា `"Hello Student!"` ដោយប្រើប្រាស់ **Implicit Intent**។
*   **ចម្លើយ៖**
    ```java
    String uriString = "smsto:" + "099888777";
    Intent intent = new Intent(Intent.ACTION_SENDTO);
    intent.setData(Uri.parse(uriString));
    intent.putExtra("sms_body", "Hello Student!");
    startActivity(intent);
    ```

