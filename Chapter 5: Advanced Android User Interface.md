# Chapter 5: Advanced Android User Interface 
## ផ្នែកទី ១៖ ខ្លឹមសារមេរៀន និងនិយមន័យលម្អិត (Lesson Contents & Definitions)

### ១. លទ្ធផលរំពឹងទុកនៃមេរៀន (Lesson Learning Outcomes - LLO)
*   **LLO1:** ពន្យល់ពីការប្រើប្រាស់ **Advance View** ដែលបង្ហាញទិន្នន័យជា **List** ឬ **Grid**។
*   **LLO2:** អនុវត្តសរសេរកូដបង្ហាញទិន្នន័យជា **List** ឬ **Grid** នៅក្នុង App។
*   **LLO3:** បង្កើត App ដែលមានបង្ហាញទិន្នន័យជា **List** ឬ **Grid**။
*   **LLO4:** សិក្សាបន្ថែមអំពីការបង្ហាញទិន្នន័យជា **List** ឬ **Grid** ដែលមានលក្ខណៈរស់រវើកជាមួយ Library ផ្សេងៗទៀត។

### ២. និយមន័យនៃ Adapter
*   **Adapter:** គឺជា**ស្ពានចម្លង (Bridge) រវាង UI components និង data sources** ដែលជួយយើងក្នុងការបំពេញទិន្នន័យទៅក្នុង UI component។ វាដើរតួជាអ្នករក្សាទុកទិន្នន័យ រួចបញ្ជូនទិន្នន័យនោះទៅកាន់ **`AdapterView`** បន្ទាប់មក View អាចទាញយកទិន្នន័យពី `AdapterView` ទៅបង្ហាញនៅលើអេក្រង់ផ្សេងៗគ្នាដូចជា **ListView, GridView, Spinner,** និង **RecyclerView**។ *(សូមមើលរូបភាពដ្យាក្រាម Adapter នៅក្នុងផ្ទាំង Studio Panel)*។

### ៣. ប្រភេទ Adapters ទូទៅ (Common Adapters)
*   **BaseAdapter:** គឺជាអាដាប់ទ័រមេ (**Parent Adapter**) សម្រាប់គ្រប់ Adapters ផ្សេងទៀតទាំងអស់។
*   **ArrayAdapter:** ប្រើប្រាស់នៅពេលដែលយើងមានបញ្ជីនៃធាតុតែមួយ (Single Items) ដែលគាំទ្រដោយ Array។
*   **Custom ArrayAdapter:** ប្រើប្រាស់នៅពេលដែលយើងត្រូវការរចនា ឬបង្ហាញបញ្ជីបែបផ្ទាល់ខ្លួន (Custom List)។
*   **SimpleAdapter:** ជាអាដាប់ទ័រដ៏ងាយស្រួលមួយក្នុងការតភ្ជាប់ទិន្នន័យឋិតិវន្ត (Static Data) ទៅកាន់ Views ដែលបានកំណត់នៅក្នុងឯកសារ XML។
*   **Custom SimpleAdapter:** ប្រើប្រាស់នៅពេលដែលយើងត្រូវការបង្ហាញបញ្ជីដែលបានរចនាឡើងជាពិសេស (Customized List) និងត្រូវការចូលទៅគ្រប់គ្រង ឬប្រើប្រាស់ child items របស់ list ឬ grid។

### ៤. ListView និងបណ្តាលក្ខណៈ Attribute ក្នុង XML
*   **ListView:** ប្រើដើម្បីបង្ហាញបញ្ជីទិន្នន័យរមៀលចុះឡើង (Scrolling List)។ យើងអាចបញ្ចូលវាទៅក្នុងប្លង់ XML បានតាមរយៈ Tag `<ListView>`។
*   **បណ្តា Attributes សំខាន់ៗក្នុង XML៖**
    *   `android:divider`: កំណត់រូបភាព ឬពណ៌សម្រាប់គូសបន្ទាត់ពុះចែករវាង list items នីមួយៗ។
    *   `android:dividerHeight`: កំណត់កម្ពស់នៃបន្ទាត់ពុះចែក (ឧទាហរណ៍៖ `2dp`)។
    *   `android:entries`: ភ្ជាប់ទៅកាន់ array resource (នៅក្នុង `arrays.xml`) ដើម្បីយកទិន្នន័យមកបំពេញក្នុង `ListView` ដោយស្វ័យប្រវត្តិតាមរយៈប្លង់ XML។
    *   `android:footerDividersEnabled` / `android:headerDividersEnabled`: កំណត់ថាតើត្រូវបង្ហាញបន្ទាត់ពុះចែកនៅពីក្រោយ Footer ឬពីមុខ Header ដែរឬទេ នៅពេលកំណត់តម្លៃជា `false`។

### ៥. ជំហាននៃការបង្កើត ListView ជាមួយ ArrayAdapter
1.  បន្ថែម Component `<ListView/>` ទៅក្នុងឯកសារប្លង់ XML `activity_main.xml`។
2.  នៅក្នុងឯកសារ `MainActivity.java` ត្រូវ៖
    *   **Define Array/ArrayList:** បង្កើត និងកំណត់តម្លៃរបស់ Array (ឧទាហរណ៍៖ ចំនួន ១០ ធាតុ)។
    *   **ArrayAdapter:** បង្កើត Instance នៃ `ArrayAdapter` ដើម្បីទាញយកទិន្នន័យពី Array និងកំណត់ប្រភេទ Layout សម្រាប់បង្ហាញ (ដូចជា `android.R.layout.simple_list_item_1`)។
    *   **setAdapter():** ហៅប្រើប្រាស់ Method `setAdapter()` នៅលើ ListView Object ដើម្បីភ្ជាប់ ArrayAdapter ចូលទៅក្នុង ListView។
    *   **setOnItemClickListener:** កំណត់ព្រឹត្តិការណ៍ចុច (Click Event) ទៅលើ List Item នីមួយៗ។

### ៦. ជំហាននៃការបង្កើត ListView ជាមួយ Custom ArrayAdapter
1.  បន្ថែម Component `<ListView/>` ទៅក្នុងឯកសារប្លង់ XML `activity_main.xml`។
2.  បង្កើតឯកសារប្លង់ XML ថ្មីមួយឈ្មោះថា **`list_item.xml`** នៅក្នុង `/res/layout` ដើម្បីកំណត់រចនាបថជួរនីមួយៗនៃ ListView (ឧទាហរណ៍៖ មាន ImageView មួយនៅខាងឆ្វេង និង TextView ពីរតម្រៀបជាជួរឈរនៅខាងស្តាំ)។
3.  បង្កើត Class Java ថ្មីមួយឈ្មោះថា **`MyListAdapter.java`** ដោយទាញយកលក្ខណៈ (Extends) ពី `ArrayAdapter<String>`។ នៅក្នុង Class នេះត្រូវសរសេរកូដជំនួស (Override) លើ Method **`getView()`** ដើម្បីធ្វើការបំលែងប្លង់ XML (Inflate) និងបញ្ជូនទិន្នន័យ (Text, Image) ទៅកាន់ View នីមួយៗតាមទីតាំង (Position)។
4.  នៅក្នុងឯកសារ `MainActivity.java` ត្រូវ៖
    *   ប្រកាសបង្កើត Arrays ចំនួន ៣ (maintitle, subtitle, imgid)។
    *   បង្កើត Instance ចេញពី `MyListAdapter` ដោយបញ្ជូនតម្លៃ Arrays ទាំងនោះទៅកាន់ Constructor។
    *   ហៅប្រើប្រាស់ `listView.setAdapter(adapter)`។
    *   កំណត់ព្រឹត្តិការណ៍ `setOnItemClickListener` ទៅលើ ListView។

### ៧. ការបញ្ជូន និងទទួលទិន្នន័យរវាង Activities (Data Transfer)
*   **ការផ្ញើទិន្នន័យ (Send):** យើងអាចបញ្ជូនទិន្នន័យទៅកាន់ Activity ផ្សេងទៀតបាន តាមរយៈ៖
    *   **`Bundle`**: បង្កើត Object `Bundle` រួចផ្ទុកទិន្នន័យជាគូ `Key/Value` (ដោយ Key ជា String) រួចផ្ញើតាមរយៈ `putExtras(bundle)`។
    *   **`putExtra()`**: ដាក់ទិន្នន័យផ្ទាល់ទៅក្នុង Intent Object ជាគូ `Key/Value`។
    *   *ប្រភេទតម្លៃដែលអាចផ្ញើបាន:* Primitive data types (int, float, ...) និង Objects ប្រភេទ String, Bundle, Parcelable, និង Serializable។
*   **ការទទួលទិន្នន័យ (Get):** អេក្រង់ទទួលអាចចូលទៅប្រើប្រាស់ទិន្នន័យទាំងនោះបានតាមរយៈការហៅ Method `getIntent()` រួចប្រើប្រាស់វិធីសាស្ត្រដូចជា `getIntent().getExtras()` សម្រាប់ Bundle ឬ `getIntent().getStringExtra("Key")` សម្រាប់ Intent object ផ្ទាល់។

### ៨. សមាសភាគសិក្សាបន្ថែម (Additional Components)
*   **RecyclerView:** ត្រូវបាន**ណែនាំឱ្យយកមកប្រើប្រាស់ជំនួសឱ្យ GridView** និង ListView សម្រាប់ការបង្ហាញទិន្នន័យដែលមានលក្ខណៈបត់បែន និងដំណើរការលឿនរហ័ស។
*   **CardView, Autocomplete TextView,** និង **Spinner** ក៏ជា UI Components កម្រិតខ្ពស់ដែលត្រូវសិក្សាបន្ថែមផងដែរ។

---

## ផ្នែកទី ២៖ កូដគំរូសំខាន់ៗ (Key Code Snippets)

### ១. សាមញ្ញ ListView នៅក្នុង XML (`activity_main.xml`)
```xml
<ListView
    android:id="@+id/list_view"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:divider="#FF0000"
    android:dividerHeight="1dp" />
```

### ២. ការបង្កើត ListView ជាមួយ ArrayAdapter ធម្មតា (Java)
```java
// ១. ប្រកាស Array ផ្ទុកទិន្នន័យ
String[] listItem = {"Android", "Java", "Php", "Python", "Ajax", "C++", "Ruby", "CSS", "HTML"};

// ២. ចាប់យក Reference របស់ ListView
ListView listView = findViewById(R.id.list_view);

// ៣. បង្កើត ArrayAdapter
ArrayAdapter<String> adapter = new ArrayAdapter<String>(this, 
    android.R.layout.simple_list_item_1, listItem);

// ៤. ភ្ជាប់ Adapter ទៅកាន់ ListView
listView.setAdapter(adapter);

// ៥. បង្កើត OnItemClickListener ពេលអ្នកប្រើប្រាស់ចុចលើ Item
listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
    @Override
    public void onItemClick(AdapterView<?> adapterView, View view, int position, long id) {
        String value = listItem[position];
        Toast.makeText(getApplicationContext(), value, Toast.LENGTH_SHORT).show();
    }
});
```

### ៣. ប្លង់រចនាជួរនីមួយៗរបស់ Custom ListView (`list_item.xml`)
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://xmlns.android.com/apk/res/android"
    android:orientation="horizontal"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <ImageView
        android:id="@+id/icon"
        android:layout_width="60dp"
        android:layout_height="60dp"
        android:padding="5dp" />

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <TextView
            android:id="@+id/title"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Medium Text"
            android:textStyle="bold"
            android:textAppearance="?android:attr/textAppearanceMedium"
            android:layout_marginLeft="10dp"
            android:layout_marginTop="5dp"
            android:padding="2dp"
            android:textColor="#4d4d4d" />

        <TextView
            android:id="@+id/subtitle"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="TextView"
            android:layout_marginLeft="10dp"/>
    </LinearLayout>
</LinearLayout>
```

### ៤. កូដថ្នាក់ `MyListAdapter.java` សម្រាប់ Custom ArrayAdapter
```java
public class MyListAdapter extends ArrayAdapter<String> {
    private final Activity context;
    private final String[] maintitle;
    private final String[] subtitle;
    private final Integer[] imgid;

    // Constructor របស់ Custom Adapter
    public MyListAdapter(Activity context, String[] maintitle, String[] subtitle, Integer[] imgid) {
        super(context, R.layout.item_list, maintitle);
        this.context = context;
        this.maintitle = maintitle;
        this.subtitle = subtitle;
        this.imgid = imgid;
    }

    @Override
    public View getView(int position, View view, ViewGroup parent) {
        // បំប្លែងប្លង់ XML ទៅជា View Object
        LayoutInflater inflater = context.getLayoutInflater();
        View rowView = inflater.inflate(R.layout.item_list, null, true);

        // ចាប់យក reference នៃ Views ក្នុង list_item.xml
        TextView titleText = (TextView) rowView.findViewById(R.id.title);
        ImageView imageView = (ImageView) rowView.findViewById(R.id.icon);
        TextView subtitleText = (TextView) rowView.findViewById(R.id.subtitle);

        // កំណត់តម្លៃទៅតាមទីតាំង Position នីមួយៗ
        titleText.setText(maintitle[position]);
        imageView.setImageResource(imgid[position]);
        subtitleText.setText(subtitle[position]);

        return rowView;
    }
}
```

### ៥. កូដដំណើរការ Custom Adapter នៅក្នុង `MainActivity.java`
```java
// ១. រៀបចំទិន្នន័យ Arrays ទាំង ៣ ប្រភេទ
String[] maintitle = {"Android", "Java", "Php", "Python", "Ajax"};
String[] subtitle = {"This is android", "This is Java", "This is PHP", "This is Python", "This is Ajax"};
Integer[] imgid = {R.drawable.android_icon, R.drawable.java_icon, R.drawable.php_icon, R.drawable.pyton_icon, R.drawable.ajax_icon};

// ២. បង្កើត Instance របស់ MyListAdapter
MyListAdapter adapter = new MyListAdapter(this, maintitle, subtitle, imgid);

// ៣. ចាប់យក reference និងកំណត់ adapter ទៅ ListView
ListView list = findViewById(R.id.list);
list.setAdapter(adapter);

// ៤. កំណត់ព្រឹត្តិការណ៍ Click
list.setOnItemClickListener(new AdapterView.OnItemClickListener() {
    @Override
    public void onItemClick(AdapterView<?> adapterView, View view, int position, long id) {
        Toast.makeText(getApplicationContext(), "Clicked index: " + position, Toast.LENGTH_SHORT).show();
    }
});
```

### ៦. កូដបញ្ជូន និងទទួលទិន្នន័យរវាង Activities
*   **ការផ្ញើតាមរយៈ Bundle៖**
    ```java
    Bundle mBundle = new Bundle();
    mBundle.putString("name", "Sokngim");
    mBundle.putInt("age", 24);

    Intent intent = new Intent(MainActivity.this, TestingActivity.class);
    intent.putExtras(mBundle);
    startActivity(intent);
    ```
*   **ការទទួលទិន្នន័យពី Bundle (ក្នុង Activity ថ្មី)៖**
    ```java
    Bundle extras = getIntent().getExtras();
    if (extras != null) {
        String name = extras.getString("name");
        int age = extras.getInt("age", 0);
        Log.d("mBundle", "Name: " + name + ", Age: " + age);
    }
    ```

---

## ផ្នែកទី ៣៖ កម្រងសំណួរសម្រាប់ប្រឡង (Exam Questions)

## ប្រភេទទី ១៖ សំណួរជ្រើសរើសចម្លើយ (Multiple Choice Questions)

**សំណួរ ១៖ តើអ្វីទៅជាតួនាទីចម្បងរបស់ "Adapter" នៅក្នុងប្រព័ន្ធ Android?**
A. ប្រើសម្រាប់រក្សាទិន្នន័យទូរស័ព្ទ  
B. ជាស្ពានចម្លងបំពេញទិន្នន័យរវាង UI components និង data sources  
C. ជាកម្មវិធីគ្រប់គ្រងបណ្តាញអ៊ីនធឺណិត  
D. ប្រើសម្រាប់ផ្លាស់ប្តូររូបរាងអេក្រង់  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 2៖ "Adapter is a bridge between UI components and data sources...")។

**សំណួរ ២៖ តើ Class មួយណាដែលជាអាដាប់ទ័រមេ (Parent Adapter) សម្រាប់បណ្តា Adapters ទាំងអស់នៅក្នុង Android?**
A. ArrayAdapter  
B. SimpleAdapter  
C. BaseAdapter  
D. ListAdapter  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 2៖ "BaseAdapter – It is parent adapter for all other adapters.")។

**សំណួរ ៣៖ តើប្រភេទ Adapter មួយណាដែលស័ក្តិសមបំផុតសម្រាប់ប្រើប្រាស់ នៅពេលទិន្នន័យដែលត្រូវបង្ហាញជាបញ្ជីធម្មតា និងគាំទ្រដោយ Array សាមញ្ញ?**
A. SimpleAdapter  
B. Custom SimpleAdapter  
C. ArrayAdapter  
D. BaseAdapter  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 2-3៖ "ArrayAdapter – It is used whenever we have a list of single items which is backed by an array.")។

**សំណួរ ៤៖ តើលក្ខណៈ Attribute មួយណាដែលប្រើសម្រាប់កំណត់ពណ៌ ឬរូបភាពចន្លោះបន្ទាត់ពុះចែករវាង list items នីមួយៗនៅក្នុង XML?**
A. `android:dividerHeight`  
B. `android:entries`  
C. `android:divider`  
D. `android:background`  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 4៖ "android:divider Drawable or color to draw between list items.")។

**សំណួរ ៥៖ តើលក្ខណៈ Attribute មួយណានៃ ListView XML ដែលអនុញ្ញាតឱ្យយើងភ្ជាប់ទៅកាន់ Array Resource ផ្ទាល់ដើម្បីបង្ហាញទិន្នន័យភ្លាមៗ?**
A. `android:entries`  
B. `android:divider`  
C. `android:id`  
D. `android:text`  
*   **ចម្លើយត្រឹមត្រូវ៖ A** (យោងតាមស្លាយទី 4៖ "android:entries Reference to an array resource that will populate the ListView.")។

**សំណួរ ៦៖ នៅក្នុងការបង្កើត Custom ArrayAdapter តើ Method មួយណាដែលត្រូវធ្វើការសរសេរកូដជំនួស (Override) ដើម្បីរចនាប្លង់ជួរ និងបញ្ចូលទិន្នន័យតាម Position?**
A. `onCreate()`  
B. `getView(int position, View view, ViewGroup parent)`  
C. `setAdapter()`  
D. `onItemClick()`  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 15៖ "public View getView(int position, View view, ViewGroup parent) ... return rowView;")។

**សំណួរ ៧៖ តើ Component មួយណាដែលត្រូវបានណែនាំឱ្យយកមកប្រើប្រាស់ជំនួសឱ្យ GridView នៅក្នុង Android?**
A. ListView  
B. ScrollView  
C. RecyclerView  
D. WebView  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 2៖ "RecyclerView has been suggested for use instead of GridView.")។

**សំណួរ ៨៖ តើ Key សម្រាប់ការបញ្ជូនទិន្នន័យ (Data Passing) រវាង Activities តាមរយៈ Extras ត្រូវតែមានប្រភេទជាអ្វី?**
A. Integer  
B. Character  
C. String  
D. Boolean  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយទី 8៖ "The key is always of type String.")។

**សំណួរ ៩៖ តើប្រភេទ Objects ណាខ្លះដែលអាចបញ្ជូនជាតម្លៃ (Value) រវាង Activities តាមរយៈ Intent extras?**
A. String និង Bundle  
B. Parcelable និង Serializable  
C. គ្រប់ប្រភេទ Primitive data types  
D. គ្រប់ជម្រើសខាងលើទាំងអស់  
*   **ចម្លើយត្រឹមត្រូវ៖ D** (យោងតាមស្លាយទី 8៖ "...use the primitive data types... plus objects of type String, Bundle, Parcelable and Serializable.")។

**សំណួរ ១០៖ នៅអេក្រង់ទទួលទិន្នន័យ តើត្រូវហៅ Method ណាមួយរបស់ Intent ដើម្បីអាចទាញយកទិន្នន័យ String មកប្រើប្រាស់?**
A. `getIntent().getBundle()`  
B. `getIntent().getStringExtra(String key)`  
C. `getIntent().getData()`  
D. `getIntent().getAction()`  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយទី 10៖ "String name= getIntent().getStringExtra(“name”);")។

---

## ប្រភេទទី ២៖ សំណួរសរសេរ និងដោះស្រាយកូដ (Structured & Coding Questions)

**សំណួរ ១៖** ចូរពន្យល់ពីនិយមន័យរបស់ **Adapter** និងប្រាប់ពីរបៀបដែលវាដំណើរការដើម្បីបង្ហាញទិន្នន័យនៅលើ `ListView`។
*   **ចម្លើយ៖** Adapter គឺជាស្ពានចម្លង (Bridge) រវាង UI components និង data sources (ដូចជា Array, List, DB)។ វាមានតួនាទីជាអ្នកផ្ទុកទិន្នន័យទាំងនោះ ហើយបំលែងជួរនីមួយៗឱ្យទៅជា View Object រួចបញ្ជូនទៅកាន់ `AdapterView` ដើម្បីឱ្យ `ListView` អាចទាញយកទៅបង្ហាញនៅលើអេក្រង់ទូរស័ព្ទ។

**សំណួរ ២៖** ចូរសរសេរកូដ Java ដើម្បីបង្កើត `ArrayAdapter` ធម្មតាមួយដែលមានឈ្មោះថា `myAdapter` ដោយយកទិន្នន័យពី Array ឈ្មោះ `fruits` (ដែលមានតម្លៃ `"Apple"`, `"Banana"`, `"Mango"`) និងប្រើប្រាស់ប្លង់លំនាំដើម `simple_list_item_1` របស់ Android។
*   **ចម្លើយ៖**
    ```java
    String[] fruits = {"Apple", "Banana", "Mango"};
    ArrayAdapter<String> myAdapter = new ArrayAdapter<String>(this, 
        android.R.layout.simple_list_item_1, fruits);
    ```

**សំណួរ ៣៖** ចូរសរសេរកូដ XML សម្រាប់បង្កើត `ListView` មួយដែលមាន ID `@+id/custom_list` ដោយកំណត់កម្ពស់នៃបន្ទាត់ពុះចែកជួរ (divider height) ទំហំ `2dp` និងមានបន្ទាត់ពុះចែកពណ៌ប្រផេះ (`#CCCCCC`)។
*   **ចម្លើយ៖**
    ```xml
    <ListView
        android:id="@+id/custom_list"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:divider="#CCCCCC"
        android:dividerHeight="2dp" />
    ```

**សំណួរ ៤៖** នៅក្នុង Class `MyListAdapter` របស់ Custom ArrayAdapter ចូរសរសេរកូដបំពេញបន្ថែមនៅក្នុង Method `getView()` ដើម្បីធ្វើការបំលែងប្លង់ XML `R.layout.item_list` ទៅជា View Object និងទាញយក Reference របស់ TextView មួយដែលមាន ID `@id/title`។
*   **ចម្លើយ៖**
    ```java
    @Override
    public View getView(int position, View view, ViewGroup parent) {
        // បំលែងប្លង់ XML ទៅជា View
        LayoutInflater inflater = context.getLayoutInflater();
        View rowView = inflater.inflate(R.layout.item_list, null, true);

        // ទាញយក reference របស់ TextView
        TextView titleText = (TextView) rowView.findViewById(R.id.title);
        
        return rowView;
    }
    ```

**សំណួរ ៥៖** ចូរសរសេរកូដ Java សម្រាប់ការបញ្ជូនទិន្នន័យពីរគឺ `course_name` (តម្លៃ: `"Mobile Dev"`) និង `credit_hour` (តម្លៃ: `3`) ពី `MainActivity` ទៅកាន់ `DetailActivity` តាមរយៈវិធីសាស្ត្រ `putExtra()` ផ្ទាល់របស់ Intent Object។
*   **ចម្លើយ៖**
    ```java
    Intent intent = new Intent(MainActivity.this, DetailActivity.class);
    intent.putExtra("course_name", "Mobile Dev");
    intent.putExtra("credit_hour", 3);
    startActivity(intent);
    ```

