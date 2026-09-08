# ផ្នែកទី ១៖ ខ្លឹមសារមេរៀនលម្អិត (Lesson Contents)

### ១. និយមន័យគ្រឹះនៃ Views និង Layouts
*   **Layout (ប្លង់):** គឺជាអ្នកកំណត់រចនាសម្ព័ន្ធសម្រាប់ User Interface (UI) នៅក្នុងកម្មវិធី ដូចជាការកំណត់ទម្រង់នៅក្នុង Activity។
*   **Hierarchy:** រាល់ធាតុផ្សំ (Elements) ទាំងអស់នៅក្នុង Layout ត្រូវបានបង្កើតឡើងដោយប្រើប្រាស់ឋានានុក្រមនៃ Objects ពីរប្រភេទគឺ **View** និង **ViewGroup**។
*   **View vs ViewGroup:** 
    *   **View:** គឺជា Component ឯកត្តជន (Widget) ដែលបង្ហាញនៅលើអេក្រង់ (ដូចជា TextView, EditText, Button)។
    *   **ViewGroup:** គឺជា Container ពិសេសដែលអាចផ្ទុក និងរៀបចំទីតាំងរបស់ Views ផ្សេងទៀត (ឬ ViewGroup ផ្សេងទៀត) នៅខាងក្នុងវា។

### ២. ប្រភេទ UI Layouts សំខាន់ៗ (Common Layouts)
*   **LinearLayout:** គឺជា Layout ទូទៅដែលតម្រៀប Views ឬ Components ជាជួរដេក (**Horizontal**) ឬជាជួរឈរ (**Vertical**)។
    *   ការតម្រៀបគឺធ្វើឡើងតាមរយៈ Attribute: `android:orientation`។
    *   សម្រាប់ជួរដេក៖ `android:orientation="horizontal"`។
    *   សម្រាប់ជួរឈរ៖ `android:orientation="vertical"`។
*   **RelativeLayout:** អនុញ្ញាតឱ្យយើងកំណត់ទីតាំងរបស់ Components ដោយផ្អែកលើទីតាំងរបស់ Components ដែលនៅជិតខាង (Relative/Sibling) ឬផ្អែកលើ Layout មេ (Parent)។ វាជា Layout ដែលមានភាពបត់បែនខ្ពស់បំផុត និងអនុញ្ញាតឱ្យដាក់ Components នៅកន្លែងណាក៏បាន។
    *   ការកំណត់ទិសដៅរៀបចំប្រើប្រាស់ពាក្យគន្លឹះដូចជា៖ `"above, below, left, right"` (ឬ `toRightOf`, `alignParentRight`)។
*   **WebView:** គឺជា View ពិសេសមួយដែលប្រើសម្រាប់បង្ហាញទំព័រ Web Page នៅខាងក្នុងកម្មវិធី Android។ វាអាចផ្ទុក URL ឬខ្សែអក្សរ HTML (HTML string) ដើម្បីបង្ហាញ ហើយវាអាចបំប្លែងកម្មវិធីរបស់អ្នកទៅជា Web Application បាន។
    *   **បណ្តា Methods សំខាន់ៗរបស់ WebView៖**
        *   `canGoBack()`: បញ្ជាក់ថា តើ WebView មានប្រវត្តិដើរថយក្រោយ (back history) ឬទេ។
        *   `canGoForward()`: បញ្ជាក់ថា តើ WebView មានប្រវត្តិដើរទៅមុខ (forward history) ឬទេ។
        *   `clearHistory()`: សម្អាតប្រវត្តិនៃការដើរទៅមុខ និងថយក្រោយ Thread។
        *   `destroy()`: បំផ្លាញ State ខាងក្នុងរបស់ WebView។
        *   `findAllAsync(String find)`: ស្វែងរកគ្រប់ពាក្យដែលត្រូវគ្នានិងធ្វើការ highlight។
        *   `getProgress()`: ទទួលយកតម្លៃ Progress នៃទំព័របច្ចុប្បន្ន។
        *   `getTitle()`: ត្រឡប់មកវិញនូវ Title នៃទំព័របច្ចុប្បន្ន។
        *   `getUrl()`: ត្រឡប់មកវិញនូវ URL នៃទំព័របច្ចុប្បន្ន។

### ៣. UI Components (Widgets) សំខាន់ៗ
*   **TextView:** ជា Component សម្រាប់បង្ហាញអត្ថបទ (Label/Caption) នៅលើកម្មវិធី វាមិនអាចកែសម្រួលបានឡើយ (not editable) និងមិនទទួលយកការបញ្ចូលព័ត៌មានពីអ្នកប្រើប្រាស់ (takes no input)។
*   **EditText:** ជា Subclass របស់ TextView ដែលត្រូវបានបន្ថែមមុខងារឱ្យអាចកែសម្រួលបាន (editable) ដើម្បីឱ្យអ្នកប្រើប្រាស់អាចបញ្ចូលទិន្នន័យ dynamically បាន។
*   **Button:** ជា Component សម្រាប់ឱ្យអ្នកប្រើប្រាស់ចុច ឬសង្កត់ (pushed/pressed/clicked) ដើម្បីធ្វើសកម្មភាពអ្វីមួយ។
*   **ImageView:** ប្រើសម្រាប់បង្ហាញរូបភាពនៅក្នុងកម្មវិធី។ វាមានសារៈសំខាន់ក្នុងការរចនា UI ឱ្យមានភាពទាក់ទាញ ប៉ុន្តែពិបាកគ្រប់គ្រងដោយសារទំហំអេក្រង់ទូរស័ព្ទ Android មានច្រើនខុសៗគ្នា។
*   **ImageButton:** ប្រើសម្រាប់បង្ហាញប៊ូតុងធម្មតា ប៉ុន្តែមានរូបភាពនៅពីលើ ដែលអ្នកប្រើប្រាស់អាចចុចបាន។ តាមលំនាំដើម វាមើលទៅដូចប៊ូតុងធម្មតា ប៉ុន្តែផ្ទៃខាងក្រោយរបស់វាអាចផ្លាស់ប្តូរពណ៌ទៅតាម State ផ្សេងៗគ្នានៃប៊ូតុង។
*   **CheckBox:** ជាប្រភេទប៊ូតុងដែលមានពីរ State គឺ Checked (ជ្រើសរើស) ឬ Unchecked (មិនជ្រើសរើស)។ វាមានថ្នាក់មេ (Parent Class) ឈ្មោះថា **CompoundButton**។ វាត្រូវបានគេប្រើប្រាស់យ៉ាងច្រើន ដូចជាក្នុងតារាងស្ទង់មតិ ឬប្រអប់ "Remember me" នៅក្នុង Login Form។
*   **Toggle Button / Switch:** ប្រើសម្រាប់បង្ហាញ State បើក/បិទ (On/Off)។

### ៤. លក្ខណៈ Attribute សំខាន់ៗរបស់ Components
*   **លក្ខណៈរួម (Common Attributes):**
    *   `android:id`: កូដសម្គាល់តែមួយគត់ (Unique ID) សម្រាប់ Component នីមួយៗ។
    *   `android:text`: អត្ថបទដែលត្រូវបង្ហាញ។
    *   `android:textSize`: ទំហំអត្ថបទ (ជាទូទៅណែនាំឱ្យប្រើឯកតា **"sp"** សម្រាប់ scaled-pixels)។
    *   `android:textColor`: ពណ៌អត្ថបទ ដែលកំណត់ជាទម្រង់ hex (ដូចជា `"#rgb"`, `"#argb"`, `"#rrggbb"`, `"#aarrggbb"`)។
    *   `android:textStyle`: ស្តាយអត្ថបទ ដូចជា `bold`, `italic`, `normal` (បើចង់ប្រើពីររួមគ្នា ត្រូវប្រើសញ្ញា `"|"` ដូចជា `bold|italic`)។
    *   `android:gravity`: កំណត់ការតម្រឹម (Alignment) នៃអត្ថបទ ឬ Component។
    *   `android:background`: កំណត់ពណ៌ផ្ទៃខាងក្រោយ ឬរូបភាព (drawable) ផ្ទៃខាងក្រោយ។
    *   `android:visibility`: គ្រប់គ្រងការបង្ហាញខ្លួនរបស់ View (Visible, Invisible, Gone)។
    *   `android:padding`: កំណត់គម្លាតពីខាងក្នុង (គម្លាតពីគែមទៅនឹង Content) ដូចជា `paddingLeft`, `paddingRight`, `paddingTop`, `paddingBottom`។
*   **លក្ខណៈជាក់លាក់ (Specific Attributes):**
    *   **EditText:** `android:hint` (អត្ថបទបង្ហាញជាជំនួយ/Placeholder), `android:inputType` (ប្រភេទនៃការបញ្ចូល ដូចជា "text" ឬ "password"), `android:ems` (កំណត់ប្រវែងលំនាំដើមនៃប្រអប់បញ្ចូល)។
    *   **Button:** `android:onClick` (ឈ្មោះ Method នៅក្នុង Java ដែលត្រូវហៅមកប្រើពេលចុច)។
    *   **ImageView / ImageButton:** `android:src` (កំណត់ប្រភពរូបភាព/Image Source ពី drawable), `android:scaleType` (កំណត់របៀបបង្រួម ឬពង្រីករូបភាពឱ្យត្រូវនឹងទំហំ View ដូចជា `fit_xy`, `center_crop`, `fitStart`)។
    *   **CheckBox:** `android:checked` (កំណត់ State លំនាំដើមឱ្យជ្រើសរើសជាស្រេច យកតម្លៃ `true` ឬ `false`)។

### ៥. យន្តការ Event Handling និង Event Listener
*   **Event Listener:** គឺជា Interface នៅក្នុងថ្នាក់ `View` ដែលមានផ្ទុកនូវ **Callback Method តែមួយគត់ (Single Callback Method)**។ Method ទាំងនេះត្រូវបានហៅដោយ Android Framework នៅពេលដែលមានអន្តរកម្មកើតឡើងពីអ្នកប្រើប្រាស់។
*   **ប្រភេទ Event Listener ផ្សេងៗ៖**
    *   `onClick()`: ចេញពី Interface `View.OnClickListener`។ ហៅឡើងនៅពេលអ្នកប្រើប្រាស់ចុចលើ Component។
    *   `onCheckedChange()`: ចេញពី Interface `CompoundButton.OnCheckedChangeListener`។ ប្រើសម្រាប់ Compound Button ដែលមាន ២ State (ដូចជា CheckBox, Radio Button, Switch, Toggle Button) នៅពេលដែល State របស់វាផ្លាស់ប្តូរ។
    *   `onLongClick()`: ហៅឡើងនៅពេលដែលអ្នកប្រើប្រាស់ចុចសង្កត់ជាប់ (Long press)។
    *   `onKey()`: ចេញពី Interface `View.OnKeyListener`។ ហៅឡើងនៅពេលអ្នកប្រើប្រាស់ចុច ឬព្រលែងប៊ូតុង Hardware របស់ឧបករណ៍។
    *   `onTouch()`: ចេញពី Interface `View.OnTouchListener`។ ហៅឡើងនៅពេលមានចលនាប៉ះ ព្រលែង ឬអូសនៅលើអេក្រង់។

### ៦. Notification Components (Toast vs Snackbar)
*   **Toast:** គឺជាសារលោតបង្ហាញសាមញ្ញ (Feedback) ក្នុងទំហំតូចមួយ ក្នុងរយៈពេលខ្លី ហើយវានឹងបាត់ទៅវិញដោយស្វ័យប្រវត្តិតាមពេលវេលាកំណត់។ នៅពេលវាបង្ហាញ អ្នកប្រើប្រាស់នៅតែអាចចុចបញ្ជាកម្មវិធីបានធម្មតា។
    *   *Syntax:* `Toast toast = Toast.makeText(context, Text, Duration); toast.show();`
*   **Snackbar:** គឺជា Component ថ្មីដែលត្រូវបានណែនាំនៅក្នុង **Material Design Library** ដើម្បីជំនួសឱ្យ Toast។
    *   *ការប្រើប្រាស់:* ត្រូវបន្ថែមទម្រង់ dependency នៅក្នុង Gradle: `implementation 'com.google.android.material:material:1.2.1'`។
*   **ភាពខុសគ្នារវាង Toast និង Snackbar៖**
    1.  **ទីតាំងបង្ហាញ:** Toast អាចកែសម្រួលដើម្បីបង្ហាញនៅកន្លែងណាក៏បាននៅលើអេក្រង់ (ប្រើប្រាស់ Gravity) ប៉ុន្តែ Snackbar អាចបង្ហាញបានតែនៅប៉ែកខាងក្រោមបង្អស់នៃអេក្រង់ប៉ុណ្ណោះ។
    2.  **ប៊ូតុងសកម្មភាព (Action Button):** Toast គ្មានប៊ូតុងសកម្មភាពឡើយ ខណៈពេលដែល Snackbar អាចមានប៊ូតុងសកម្មភាពជាជម្រើស (Action Button) ប៉ុន្តែមិនគួរមានលើសពីមួយទេ។
    3.  **ការបិទសារ:** Toast មិនអាចបិទបានទេ លុះត្រាតែអស់កំណត់ម៉ោងរបស់វា ខណៈពេលដែល Snackbar អាចឱ្យអ្នកប្រើប្រាស់អូសដើម្បីបិទបាន (Swiped off) មុនពេលកំណត់ម៉ោងចប់។

### ៧. Android Logging (Log Class) និង Logcat
*   ថ្នាក់ **Log** អនុញ្ញាតឱ្យយើងបង្កើតសារ Log ដើម្បីបង្ហាញនៅក្នុងប្រព័ន្ធ **Logcat** សម្រាប់ស៊ើបអង្កេតកំហុស (Debugging)។
*   **កម្រិតនៃ Log (Log Priority) ពីខ្ពស់ទៅទាប (ឬពីតិចទៅច្រើន - least to most verbose)៖**
    1.  `Log.e(String tag, String msg)` (Error)
    2.  `Log.w(String tag, String msg)` (Warning)
    3.  `Log.i(String tag, String msg)` (Information)
    4.  `Log.d(String tag, String msg)` (Debug)
    5.  `Log.v(String tag, String msg)` (Verbose)

---

# ផ្នែកទី ២៖ កូដគំរូសំខាន់ៗ (Key Code Snippets)

### ១. LinearLayout គំរូ (XML)
*   **Horizontal Layout (ជួរដេក)៖**
    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="horizontal" >

        <Button
            android:id="@+id/button1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 1" />

        <Button
            android:id="@+id/button2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 2" />

        <Button
            android:id="@+id/button3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 3"
            android:layout_weight="1" />
    </LinearLayout>
    ```

*   **Vertical Layout (ជួរឈរ)៖**
    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical" >

        <Button
            android:id="@+id/button1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 1" />

        <Button
            android:id="@+id/button2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 2" />

        <Button
            android:id="@+id/button3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 3"
            android:layout_weight="1" />
    </LinearLayout>
    ```

### ២. RelativeLayout គំរូ (XML)
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent" >

    <Button
        android:id="@+id/btnButton1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button 1" />

    <Button
        android:id="@+id/btnButton2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button 2"
        android:layout_toRightOf="@+id/btnButton1" />

    <Button
        android:id="@+id/btnButton3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button 3"
        android:layout_below="@+id/btnButton1" />

    <Button
        android:id="@+id/btnSubmit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentRight="true"
        android:layout_below="@+id/btnButton3"
        android:text="Submit" />
</RelativeLayout>
```

### ៣. WebView គំរូ (XML & Java)
*   **XML:**
    ```xml
    <WebView xmlns:android="http://schemas.android.com/apk/res/android"
        android:id="@+id/webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
    ```
*   **Java (សរសេរក្នុង onCreate):**
    ```java
    WebView browser = findViewById(R.id.webview);
    browser.loadUrl("http://www.tutorialspoint.com");
    ```

### ៤. Responding to Click Events & Toast (Java)
```java
Button button = findViewById(R.id.button_send);
button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        Toast.makeText(MainActivity.this, "Hello Everyonee.", Toast.LENGTH_LONG).show();
    }
});
```

### ៥. Snackbar with Action Callback (Java)
```java
Snackbar snackbar = Snackbar.make(coordinatorLayout, "Message is deleted", Snackbar.LENGTH_LONG)
    .setAction("UNDO", new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            Snackbar snackbar1 = Snackbar.make(coordinatorLayout, "Message is restored!", Snackbar.LENGTH_SHORT);
            snackbar1.show();
        }
    });
snackbar.show();
```

---

# ផ្នែកទី ៣៖ កម្រងសំណួរ និងលំហាត់សម្រាប់ប្រឡង (Exam Questions)

## ប្រភេទទី ១៖ សំណួរជ្រើសរើសចម្លើយ (Multiple Choice Questions)

**សំណួរ ១៖ តើធាតុផ្សំរចនាសម្ព័ន្ធ UI របស់ Android ត្រូវបានបង្កើតឡើងដោយប្រើប្រាស់ឋានានុក្រមនៃ Objects អ្វីខ្លះ?**
A. Activity និង Intent  
B. View និង ViewGroup  
C. Java និង XML  
D. Gradle និង Manifest  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 2៖ "All elements in the layout are built using a hierarchy of View and ViewGroup objects")។

**សំណួរ ២៖ តើ Attribute មួយណាដែលប្រើសម្រាប់កំណត់ការតម្រៀប Components ជាជួរដេក ឬជួរឈរនៅក្នុង LinearLayout?**
A. `android:gravity`  
B. `android:layout_weight`  
C. `android:orientation`  
D. `android:layout_gravity`  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 3៖ "The component is arranged via the orientation attribute")។

**សំណួរ ៣៖ ប្រសិនបើលោកអ្នកចង់ឱ្យ LinearLayout រៀបចំ Views តម្រៀបពីលើចុះក្រោម (ជួរឈរ) តើត្រូវកំណត់តម្លៃ Attribute ដូចម្តេច?**
A. `android:orientation="horizontal"`  
B. `android:orientation="vertical"`  
C. `android:orientation="top_down"`  
D. `android:orientation="vertical_align"`  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 3៖ "FOR VERTICAL ARRANGEMENT android:orientation=\"vertical\"")។

**សំណួរ ៤៖ តើ Layout មួយណាដែលមានភាពបត់បែនបំផុតក្នុងការកំណត់ទីតាំង Component ទៅតាម Component ជិតខាង ឬ Parent?**
A. LinearLayout  
B. AbsoluteLayout  
C. RelativeLayout  
D. FrameLayout  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 6៖ "RelativeLayout lets you position your component based on the nearby Component's... It's the most flexible layout...")។

**សំណួរ ៥៖ តើ View មួយណាដែលប្រើប្រាស់ដើម្បីបង្ហាញទំព័រ Web Page នៅខាងក្នុងកម្មវិធី?**
A. ImageView  
B. WebView  
C. PageView  
D. BrowserView  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 8៖ "WebView is a view that displays web pages inside your application")។

**សំណួរ ៦៖ តើភាពខុសគ្នារវាង TextView និង EditText គឺជាអ្វី?**
A. TextView អាចបញ្ចូលទិន្នន័យបាន ចំណែក EditText មិនអាចបញ្ចូលទិន្នន័យបានទេ  
B. TextView ប្រើសម្រាប់បង្ហាញរូបភាព ចំណែក EditText បង្ហាញអត្ថបទ  
C. TextView ប្រើសម្រាប់បង្ហាញអត្ថបទ និងមិនអាចកែសម្រួលបានឡើយ ចំណែក EditText អាចកែសម្រួលបាន និងអនុញ្ញាតឱ្យបញ្ចូលទិន្នន័យ dynamically  
D. គ្មានចំណុចខុសគ្នាទេ  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 11, 12 & 14)។

**សំណួរ ៧៖ តើ CheckBox នៅក្នុង Android មានថ្នាក់មេ (Parent Class) ឈ្មោះអ្វី?**
A. Button  
B. CompoundButton  
C. CheckButton  
D. View  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 22៖ "CompoundButton is the parent class of CheckBox class")។

**សំណួរ ៨៖ តើ Event Listener គឺជាអ្វី?**
A. Class មួយដែលប្រើសម្រាប់គ្រប់គ្រងបណ្តាញអ៊ីនធឺណិត  
B. Interface នៅក្នុងថ្នាក់ View ដែលផ្ទុកនូវ Callback Method តែមួយគត់សម្រាប់ដោះស្រាយ Event  
C. ប៊ូតុងពិសេសសម្រាប់ចុចបញ្ជាសំឡេង  
D. គ្មានចម្លើយត្រឹមត្រូវ  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 26៖ "An event listener is an interface in the View class that contains a single callback method")។

**សំណួរ ៩៖ តើចរិតលក្ខណៈមួយណាដែលជាភាពខុសគ្នារវាង Toast និង Snackbar?**
A. Toast អាចមានប៊ូតុង Action ចំណែក Snackbar គ្មានទេ  
B. Toast បង្ហាញនៅតែប៉ែកខាងក្រោមនៃអេក្រង់ ចំណែក Snackbar អាចបង្ហាញបានគ្រប់កន្លែង  
C. Toast មិនអាចបិទបានឡើយទាល់តែអស់កំណត់ម៉ោង ខណៈពេលដែល Snackbar អាចឱ្យអ្នកប្រើប្រាស់អូសដើម្បីបិទបាន (Swiped off)  
D. Toast ត្រូវការបន្ថែម Material library ដើម្បីដំណើរការ  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 34៖ "Toast message cannot be off until the time limit finish, but Snackbar can be swiped off before the time limit")។

**សំណួរ ១០៖ យោងតាមកម្រិតអាទិភាព (Priority) នៃ Log នៅក្នុង Android តើវិធីសាស្ត្រ (Method) មួយណាដែលមានអាទិភាពទាបជាងគេបំផុត (verbose បំផុត)?**
A. `Log.e()`  
B. `Log.d()`  
C. `Log.i()`  
D. `Log.v()`  
*   **ចម្លើយត្រឹមត្រូវ៖ D** (យោងតាមស្លាយទី 35៖ "Log methods listed in order from the highest to lowest priority... Log.v(String, String) (verbose)")។

---

## ប្រភេទទី ២៖ សំណួរសរសេរ និងដោះស្រាយកូដ (Structured & Coding Questions)

**សំណួរ ១៖** ចូរពន្យល់ពីភាពខុសគ្នារវាង `padding` និង `scaleType` នៅក្នុង `ImageView` និងការប្រើប្រាស់របស់វា។
*   **ចម្លើយ៖**
    *   **android:padding:** ត្រូវបានប្រើសម្រាប់កំណត់គម្លាតពីផ្នែកគែមទាំងសងខាង (ឆ្វេង ស្ដាំ លើ ក្រោម) នៃ `ImageView` ទៅកាន់រូបភាពដែលបង្ហាញនៅខាងក្នុងវា។
    *   **android:scaleType:** ត្រូវបានប្រើប្រាស់ដើម្បីគ្រប់គ្រង ឬកំណត់របៀបដែលរូបភាពត្រូវបង្រួម ឬពង្រីក (re-sized) ឬផ្លាស់ទីដើម្បីឱ្យសមស្របទៅនឹងទំហំរបស់ប្រអប់ `ImageView` នោះ។ តម្លៃរបស់វាមានដូចជា `fit_xy`, `center_crop`, `fitStart` ជាដើម។

**សំណួរ ២៖** ចូរសរសេរកូដ Java ដើម្បីចាប់យក Reference របស់ `WebView` ដែលមាន ID `webview` ពី XML រួចបញ្ជាឱ្យវា Load ទៅកាន់ទំព័រ website ឈ្មោះ `"http://www.tutorialspoint.com"`។
*   **ចម្លើយ៖**
    ```java
    // ចាប់យក reference ពី XML មក Java
    WebView browser = findViewById(R.id.webview);
    // Load URL ចូលទៅក្នុង WebView
    browser.loadUrl("http://www.tutorialspoint.com");
    ```

**សំណួរ ៣៖** ចូរសរសេរ XML កូដដើម្បីបង្កើត `EditText` មួយដែលមាន ID `@+id/username_input` ទំហំទទឹងពេញអេក្រង់ និងកំពស់សមស្របតាមទំហំអត្ថបទ ដោយមានអត្ថបទជំនួយ (Placeholder) បង្ហាញពាក្យថា `"Enter Username"` និងកំណត់ប្រភេទបញ្ចូលជាអក្សរធម្មតា។
*   **ចម្លើយ៖**
    ```xml
    <EditText
        android:id="@+id/username_input"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Username"
        android:inputType="text" />
    ```

**សំណួរ ៤៖** ចូរសរសេរកូដ Java នៅក្នុង `onCreate()` ដើម្បីបង្កើត Button មួយដែលមាន ID `@+id/btn_toast` នៅពេលអ្នកប្រើប្រាស់ចុចលើប៊ូតុងនេះ វានឹងលោតសារ Toast បង្ហាញពាក្យថា `"Hello, Android!"` ក្នុងរយៈពេលវែង។
*   **ចម្លើយ៖**
    ```java
    Button button = findViewById(R.id.btn_toast);
    button.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            Toast.makeText(MainActivity.this, "Hello, Android!", Toast.LENGTH_LONG).show();
        }
    });
    ```

**សំណួរ ៥៖** ចូរសរសេរលំដាប់កូដបញ្ជា Log (Log priority) ទាំង ៥ ប្រភេទនៅក្នុង Android ពីអាទិភាពខ្ពស់បំផុត (Highest) ទៅទាបបំផុត (Lowest) និងពន្យល់ពីប្រភេទនីមួយៗ។
*   **ចម្លើយ៖**
    លំដាប់លំដោយពីខ្ពស់ទៅទាបមានដូចខាងក្រោម៖
    1.  `Log.e(String tag, String msg)`: Error - ប្រើសម្រាប់កត់ត្រាកំហុសធ្ងន់ធ្ងរដែលធ្វើឱ្យកម្មវិធីគាំង។
    2.  `Log.w(String tag, String msg)`: Warning - ប្រើសម្រាប់សារព្រមានអំពីបញ្ហាដែលអាចកើតមាន។
    3.  `Log.i(String tag, String msg)`: Information - ប្រើសម្រាប់កត់ត្រាព័ត៌មានទូទៅនៃដំណើរការកម្មវិធី។
    4.  `Log.d(String tag, String msg)`: Debug - ប្រើសម្រាប់បង្ហាញព័ត៌មានលម្អិតក្នុងពេលសរសេរកូដ និង Debug។
    5.  `Log.v(String tag, String msg)`: Verbose - ប្រើសម្រាប់ព័ត៌មានលម្អិតបំផុតគ្រប់ជំហានដែលគ្មានការរឹតត្បិត (អាទិភាពទាបបំផុត)។

---
