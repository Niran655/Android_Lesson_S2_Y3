**១. ការប្រៀបធៀប Layout សំខាន់ៗ (ViewGroups)**

| Layout | លក្ខណៈពិសេស (Key Features) | កាតព្វកិច្ច និង Attribute សំខាន់ៗ |
| --- | --- | --- |
| **LinearLayout** | រៀបចំ Elements ជាជួរឈរ (Vertical) ឬជួរដេក (Horizontal) | `android:orientation` (vertical/horizontal)<br>

<br>`android:weightSum` & `android:layout_weight` (បែងចែកសមាមាត្រទំហំ) |
| **RelativeLayout** | រៀបចំ Element ដោយផ្អែកលើទីតាំង Child ផ្សេងទៀត ឬ Parent | `android:layout_toRightOf`, `android:layout_below`<br>

<br>`android:layout_centerInParent`, `android:layout_alignParentBottom` |
| **FrameLayout** | រៀបចំ Elements ជាន់លើគ្នា (Stack) ដោយ Element ចុងក្រោយគេនៅខាងលើ | ប្រើសម្រាប់ Hold Fragments ឬបង្ហាញ Preview ផ្សេងៗ |
| **ConstraintLayout** | Layout ទំនើប អាចបង្កើត UI ស្មុគស្មាញដោយមិនបាច់ប្រើ Nested Layout | `app:layout_constraintTop_toTopOf`<br>

<br>`app:layout_constraintLeft_toLeftOf` |

---

**២. UI Widgets ផ្ដោតលើ Attributes & Listeners**

* **TextView & EditText:**
* **Attributes:** `android:hint` (អត្ថបទជំនួយ), `android:inputType` (កំណត់ប្រភេទ Input ដូចជា `textPassword`, `number`, `textEmailAddress`), `android:maxLength`
* **TextChangeListener:** ប្រើ `addTextChangedListener` ដើម្បីចាប់ Event ពេល User កំពុងវាយបញ្ចូលអត្ថបទ។


* **Button & ImageButton:**
* **Event Listeners:** `setOnClickListener` (ចាប់ការ On Click), `setOnLongClickListener` (ចាប់ការ On Long Click)



---

**៣. សារជូនដំណឹង៖ Toast vs Snackbar**

| លក្ខណៈវិនិច្ឆ័យ | Toast | Snackbar |
| --- | --- | --- |
| **គោលបំណង** | បង្ហាញសារជូនដំណឹងធម្មតា ដោយមិនត្រូវការ Interaction | បង្ហាញសារជូនដំណឹងដែលអាចឱ្យ User ឆ្លើយតប (Interactive) |
| **ទីតាំង** | អាចប្ដូរទីតាំងបាន (`setGravity`) ប៉ុន្តែជាទូទៅនៅខាងក្រោម | បង្ហាញនៅផ្នែកខាងក្រោមនៃ Screen (Bottom edge) |
| **Action** | គ្មាន Action Button | អាចបន្ថែម Action Button បាន (ឧទាហរណ៍៖ `setAction("UNDO", listener)`) |
| **លុបចោល** | មិនអាច Swipe ដើម្បីលុបចេញ | អាច Swipe ដើម្បី Dismiss បាន |

---

**៤. ប្រព័ន្ធ Log (Android Logging API)**

| Log Level | Constant / Method | ពណ៌បង្ហាញ (Logcat) | គោលបំណងប្រើប្រាស់ |
| --- | --- | --- | --- |
| **Error** | `Log.e(TAG, msg)` | ពណ៌ក្រហម (Red) | សម្រាប់ចាប់ Error ធ្ងន់ធ្ងរ ឬ Exception Crash |
| **Warning** | `Log.w(TAG, msg)` | ពណ៌លឿង (Yellow) | សម្រាប់ព្រមានចំណុចដែលអាចមានបញ្ហា |
| **Info** | `Log.i(TAG, msg)` | ពណ៌បៃតង (Green) | សម្រាប់បង្ហាញព័ត៌មានទូទៅនៃដំណើរការ |
| **Debug** | `Log.d(TAG, msg)` | ពណ៌ខៀវ (Blue) | សម្រាប់ពិនិត្យទិន្នន័យ Flow ពេល Develop |
| **Verbose** | `Log.v(TAG, msg)` | ពណ៌ខ្មៅ/ប្រផេះ (Black) | សម្រាប់បង្ហាញព័ត៌មានលម្អិតបំផុត |

---

**៥. WebView & Internet Permission**

ដើម្បីប្រើប្រាស់ WebView ទាញយកទិន្នន័យពី Internet ត្រូវមានចំណុចចាំបាច់ចំនួន ២៖

* **សុំ Internet Permission ក្នុង `AndroidManifest.xml`:**
```xml
<uses-permission android:name="android.permission.INTERNET" />

```


* **ការកំណត់កូដ Java:**
```java
WebView webView = findViewById(R.id.webview);
// បើក JavaScript ប្រសិនបើ Web ត្រូវការ
webView.getSettings().setJavaScriptEnabled(true); 
// ដើម្បីឱ្យ Web បង្ហាញក្នុង App ដោយមិនបើក Chrome Browser
webView.setWebViewClient(new WebViewClient()); 
webView.loadUrl("https://www.google.com");

```



---

**៦. កូដគំរូអនុវត្តជាក់ស្តែង (Complete Activity Example)**

```java
public class MainActivity extends AppCompatActivity {
    private static final String TAG = "MainActivityLog";
    private EditText editTextInput;
    private Button btnSubmit;
    private ConstraintLayout mainLayout;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextInput = findViewById(R.id.editTextInput);
        btnSubmit = findViewById(R.id.btnSubmit);
        mainLayout = findViewById(R.id.mainLayout);

        btnSubmit.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String input = editTextInput.getText().toString().trim();

                if (input.isEmpty()) {
                    Log.w(TAG, "User input is empty");
                    Toast.makeText(MainActivity.this, "Please enter text", Toast.LENGTH_SHORT).show();
                } else {
                    Log.i(TAG, "User submitted: " + input);
                    Snackbar.make(mainLayout, "Submitted: " + input, Snackbar.LENGTH_INDEFINITE)
                            .setAction("CLEAR", new View.OnClickListener() {
                                @Override
                                public void onClick(View v) {
                                    editTextInput.setText("");
                                    Log.d(TAG, "Input cleared via Snackbar");
                                }
                            }).show();
                }
            }
        });
    }
}

```

ត
