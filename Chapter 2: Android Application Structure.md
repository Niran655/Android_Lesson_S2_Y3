#Chapter 2: Android Application Structure

## ផ្នែកទី ១៖ ខ្លឹមសារមេរៀន និងនិយមន័យលម្អិត (Lesson Contents & Definitions)

### ១. ពិពណ៌នាពីមុខងាររបស់ Android Studio Interface (ផ្អែកលើរូបភាពទី ១ និង ទី ២)
រាល់ធាតុផ្សំនៅលើអេក្រង់ Android Studio ត្រូវបានរៀបចំឡើងដើម្បីសម្រួលដល់ការសរសេរកូដ និងការរចនា UI៖
*   **Toolbar (របារឧបករណ៍):** ស្ថិតនៅផ្នែកខាងលើបង្អស់ ប្រើសម្រាប់ដំណើរការកម្មវិធី (Run App), Debug, ឬបើកគ្រប់គ្រងឧបករណ៍។
*   **Navigation Bar (របារនាំផ្លូវ):** ជួយឱ្យយើងដឹងពីទីតាំងឯកសារបច្ចុប្បន្ន និងងាយស្រួលផ្លាស់ទីរវាងឯកសារនានា។
*   **Editor Window (បង្អួចសរសេរកូដ):** ជាកន្លែងសម្រាប់សរសេរកូដ Java/Kotlin ឬកែសម្រួលប្លង់ XML។
*   **Tool Windows & Tool Window Bar:** បណ្តុំផ្ទាំងជំនួយដូចជា `Project Structur`e, `Gradle`, `Resource Manager` ដែលអាចបើកបិទបានតាមរបារសងខាង។
*   **Status Bar (របារស្ថានភាព):** បង្ហាញព័ត៌មានស្ថានភាពរបស់ Project និងសារព្រមាន ឬកំហុសផ្សេងៗ។
*   **Interface Layout Editor (ផ្ទាំងរចនាប្លង់):**
    *   **Palette:** ផ្ទុកទៅដោយ Views ឬ Widgets ផ្សេងៗ (ដូចជា Button, TextView) សម្រាប់ទាញយកទៅដាក់លើ UI។
    *   **Design Editor:** បង្ហាញគំរូអេក្រង់ទូរស័ព្ទទាំងបែបស្ងួត (Design) និងបែបកាំរស្មីអ៊ិច (Blueprint)។
    *   **Attributes (លក្ខណៈសម្បត្តិ):** ផ្ទាំងខាងស្តាំសម្រាប់កំណត់តម្លៃឱ្យ Views ដូចជា ID, ទទឹង, កម្ពស់, ពណ៌ និងអត្ថបទ។

### ២. ការបង្កើត និងប្រើប្រាស់ឧបករណ៍សាកល្បង (Tools for Testing - ផ្អែកលើរូបភាពទី ៣)
ដើម្បីដំណើរការសាកល្បងកម្មវិធី យើងមានជម្រើសពីរ៖
*   **Virtual Device (Emulator / AVD):** គឺជាទូរស័ព្ទនិម្មិតដែលបង្កើតឡើងនៅលើកុំព្យូទ័រ។
    *   *របៀបបង្កើត:* ចូលទៅកាន់ **AVD Manager** តាមរយៈ `Tools -> Android -> AVD Manager` រួចចុចលើ **Create Virtual Device**។ យើងត្រូវជ្រើសរើសទំហំអេក្រង់ (ដូចជា Nexus 6) និងទាញយកប្រព័ន្ធប្រតិបត្តិការ (System Image ដូចជា Marshmallow API 23)។
*   **Real Device (ទូរស័ព្ទពិត):** ការប្រើប្រាស់ទូរស័ព្ទពិតដើម្បីតេស្ត។
    *   *របៀបតភ្ជាប់:* ត្រូវភ្ជាប់ទូរស័ព្ទទៅកាន់កុំព្យូទ័រតាមរយៈខ្សែ **USB** និងត្រូវបើកមុខងារ **USB Debugging** នៅក្នុងទូរស័ព្ទដោយចូលទៅកាន់ `Settings -> Development Options` រួចប្រគល់សិទ្ធិ។

### ៣. ការប្រៀបធៀបឯកសារ XML និង Java (XML and Java Files)
*   **XML (Extensible Markup Language):** ប្រើប្រាស់សម្រាប់បង្កើត និងកំណត់ប្លង់អេក្រង់ (User Interface - UI)។ រាល់ Components ទាំងអស់ត្រូវបានប្រកាសជាទម្រង់ Tag នៅក្នុង Layout XML។
*   **Java:** គឺជាភាសាសរសេរកូដ (Source Code) សម្រាប់បញ្ជា និងគ្រប់គ្រងសកម្មភាពដំណើរការ (Logic & Event Handling) របស់កម្មវិធី។

### ៤. លក្ខណៈខុសគ្នារវាង DPs និង SPs (dp vs sp)
*   **dp (or dip) - Density-Independent Pixels:** គឺជាឯកតារង្វាស់ដែលមិនអាស្រ័យលើដង់ស៊ីតេអេក្រង់ទូរស័ព្ទ។ វាត្រូវបានណែនាំឱ្យ**ប្រើប្រាស់សម្រាប់គ្រប់យ៉ាងក្រៅពីទំហំអក្សរ** (ដូចជាការកំណត់ទំហំ View, padding, margins)។
*   **sp - Scale-Independent Pixels:** គឺជាឯកតាដែលប្រហាក់ប្រហែលនឹង dp ដែរ ប៉ុន្តែវាត្រូវបានពង្រីក ឬបង្រួមទៅតាមចំណង់ចំណូលចិត្តទំហំអក្សរ (Font Size Preference) របស់អ្នកប្រើប្រាស់ទូរស័ព្ទម្នាក់ៗ។ ដូចនេះ វាត្រូវបានចែងឱ្យ**ប្រើប្រាស់សម្រាប់តែទំហំអក្សរ (Text Size) ប៉ុណ្ណោះ**។

### ៥. រចនាសម្ព័ន្ធ فولឌ័រក្នុងគម្រោង (Android Application Structure)
នៅពេលយើងបើកមើល Project ក្នុងរបៀបទិដ្ឋភាព "Android" យើងនឹងឃើញរចនាសម្ព័ន្ធថតឯកសារដូចខាងក្រោម៖
*   **Manifests Folder:** មានផ្ទុកឯកសារ **`AndroidManifest.xml`** ដែលជាឯកសារគោលផ្ទុកព័ត៌មានសំខាន់ៗរបស់កម្មវិធី (ដូចជា android version, access permissions, metadata) ព្រមទាំងសមាសធាតុផ្សំរបស់ App។ វាដើរតួជាអ្នកសម្របសម្រួលទំនាក់ទំនងរវាង Android OS និងកម្មវិធី។
*   **Java Folder:** ផ្ទុកឯកសារកូដប្រភព Java (.java) ទាំងអស់។ ជាទូទៅ ឯកសារ `MainActivity.java` នឹងត្រូវបានបង្កើតឡើងដោយស្វ័យប្រវត្តិនៅក្រោមឈ្មោះកញ្ចប់ (Package Name ដូចជា com.example.firstapp)។
*   **Res Folder (Resource):** មានផ្ទុកធនធានដែលមិនមែនជាកូដ (Non-code Resources) ដូចជា រូបភាព, អក្សរ, ពណ៌, និងប្លង់រចនា។
    *   **Drawable:** ផ្ទុករូបភាពផ្សេងៗ (ដូចជា .png, .jpg) ឬ XML drawable សម្រាប់ប្រើប្រាស់ក្នុង UI (លើកលែងតែ App Launcher Icon)។
    *   **Layout:** ផ្ទុកឯកសារប្លង់ XML ទាំងអស់ដែលប្រើសម្រាប់កំណត់ UI របស់កម្មវិធី។
    *   **Mipmap:** ផ្ទុករូបតំណាងកម្មវិធី (App/Launcher Icons) ដែលត្រូវបានបែងចែកជាច្រើនទំហំដង់ស៊ីតេអេក្រង់ (hdpi, mdpi, xhdpi, xxhdpi, xxxhdpi)។
    *   **Values:** ផ្ទុកឯកសារ XML សាមញ្ញ ដូចជា `colors.xml` (ពណ៌), `strings.xml` (ខ្សែអក្សរ), `styles.xml` (ស្តាយ)។
*   **Gradle Scripts:** ត្រូវបានបង្កើតឡើងដោយស្វ័យប្រវត្តិដើម្បីកំណត់រចនាសម្ព័ន្ធនៃការចងក្រងកម្មវិធី។ វាមាន ២ ប្រភេទគឺ `build.gradle (Project)` និង `build.gradle (Module)`។

### ៦. ធនធានចម្បង និងធនធានជំនួស (App Resource vs Alternative Resource)
*   **Default Resource (ធនធានចម្បង):** ជាធនធានដែលប្រើប្រាស់ជាលក្ខណៈលំនាំដើម ឧទាហរណ៍៖ `res/layout` (សម្រាប់ទូរស័ព្ទបញ្ឈរ - Portrait)។
*   **Alternative Resource (ធនធានជំនួស):** ជាធនធានដែលត្រូវបានបង្កើតឡើងដើម្បីទ្រទ្រង់ស្ថានភាពជាក់លាក់របស់ឧបករណ៍ (ដូចជាទំហំអេក្រង់ខុសគ្នា ឬភាសាខុសគ្នា)។
    *   *ទម្រង់នៃការបង្កើត:* `<resources_name>-<config_qualifier>`។
    *   *ឧទាហរណ៍:* `res/layout-land` (សម្រាប់បង្ហាញប្លង់នៅពេលអេក្រង់ទូរស័ព្ទបង្វិលផ្តេក - Landscape)។

### ៧. ភាពខុសគ្នារវាង Style និង Theme (ផ្អែកលើរូបភាពទី ៥)
*   **Style (ស្ទីល):** គឺជាបណ្តុំ Attribute ផ្សេងៗ (ដូចជា color, size, padding) ដែលត្រូវបានកំណត់ដើម្បី**អនុវត្តទៅលើ View នីមួយៗ** (ឯកត្តជន) នៅក្នុង Layout XML។
    *   *ឧទាហរណ៍ការប្រើប្រាស់:* `style="@style/textViewStyle"`។
*   **Theme (ទម្រង់រចនា):** គឺជា Style ពិសេសមួយដែលត្រូវបាន**អនុវត្តទៅលើ Activity មួយ ឬកម្មវិធីទាំងមូល (Application)** តាមរយៈការប្រកាសនៅក្នុងឯកសារ `AndroidManifest.xml`។
    *   *ឧទាហរណ៍ការប្រើប្រាស់:* `<application android:theme="@style/AppTheme">`

### ៨. ជំហាននៃការបង្កើតកម្មវិធីប្តូរភាសា (Multi-language App - ផ្អែកលើរូបភាពទី ៤)
ដើម្បីបង្កើតកម្មវិធីដែលអាចប្តូរភាសាបាន (English, Khmer, Thai) យើងត្រូវអនុវត្តជំហានដូចខាងក្រោម៖
1.  រចនាផ្ទៃ UI ឱ្យមាន Button ចំនួន ៣ និង TextView ចំនួន ១។
2.  បង្កើត Folder ធនធានជំនួសសម្រាប់ភាសាខ្មែរ និងថៃ៖ ចុចស្តាំលើ `res` -> `New` -> `Android Resource Directory` រួចបង្កើត `values-kh` និង `values-th`។
3.  បង្កើតឯកសារ `strings.xml` នៅក្នុង Folder នីមួយៗ រួចបញ្ចូលពាក្យបកប្រែទៅតាមភាសានីមួយៗ។
4.  សរសេរកូដបង្កើត Method `setLangMethod(String localeCode)` នៅក្នុង Java ដើម្បីធ្វើការផ្លាស់ប្តូរការកំណត់ទូរស័ព្ទ (Configuration)៖
    ```java
    private void setLangMethod(String localeCode) {
        Resources resources = getResources();
        DisplayMetrics dm = resources.getDisplayMetrics();
        Configuration config = resources.getConfiguration();
        config.locale = new Locale(localeCode.toLowerCase());
        resources.updateConfiguration(config, dm);
        // កំណត់សារឡើងវិញ
        txtMessage.setText(getResources().getString(R.string.hello));
    }
    ```
5.  ហៅប្រើប្រាស់ Method ខាងលើនៅក្នុងព្រឹត្តិការណ៍ចុចប៊ូតុង `clickOnButton(View view)`។

---

## ផ្នែកទី ២៖ កម្រងសំណួរ និងលំហាត់សម្រាប់ប្រឡង (Exam Questions)

## ប្រភេទទី ១៖ សំណួរជ្រើសរើសចម្លើយ (Multiple Choice Questions)

**សំណួរ ១៖ តើផ្នែកមួយណានៃ Android Studio Interface ដែលប្រើប្រាស់សម្រាប់ដំណើរការកម្មវិធី (Run App) និងស៊ើបអង្កេតកំហុស (Debug)?**
A. Editor window  
B. Status Bar  
C. Toolbar  
D. Navigation bar  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ២៖ ប្រសិនបើអ្នកចង់តេស្តកម្មវិធីនៅលើទូរស័ព្ទពិត តើអ្នកត្រូវបើកដំណើរការមុខងារអ្វីនៅលើទូរស័ព្ទដៃរបស់អ្នក?**
A. AVD Manager  
B. USB Debugging  
C. Gradle build  
D. Local properties  
*   **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ៣៖ តើឯកតា "sp" (scale-independent pixels) ត្រូវបានណែនាំឱ្យប្រើប្រាស់សម្រាប់អ្វីខ្លះ?**
A. កម្ពស់ និងទទឹងរបស់ View  
B. Padding របស់ Layout  
C. ទំហំអក្សរ (Text Size)  
D. ពណ៌របស់អត្ថបទ  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៤៖ តើឯកសារមួយណាដែលមានផ្ទុកព័ត៌មានសិទ្ធិអនុញ្ញាត (Permissions), Version របស់កម្មវិធី និងការប្រកាសពីសមាសធាតុផ្សំរបស់កម្មវិធី?**
A. build.gradle  
B. styles.xml  
C. AndroidManifest.xml  
D. MainActivity.java  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៥៖ តើរូបតំណាងកម្មវិធី (App/Launcher Icons) ត្រូវរក្សាទុកនៅក្នុង فولឌ័រមួយណា?**
A. drawable folder  
B. mipmap folder  
C. values folder  
D. layout folder  
*   **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ៦៖ ប្រសិនបើលោកអ្នកចង់បង្កើតប្លង់រចនាសម្រាប់កម្មវិធីដែលបង្ហាញនៅពេលបង្វិលអេក្រង់ផ្តេក (Landscape) តើ فولឌ័រជំនួសមួយណាដែលត្រូវបង្កើតឡើង?**
A. `res/layout-land`  
B. `res/layout-port`  
C. `res/values-land`  
D. `res/layout-landscapes`  
*   **ចម្លើយត្រឹមត្រូវ៖ A**

**សំណួរ ៧៖ តើការកំណត់លក្ខណៈ View (ដូចជា ពណ៌ ទំហំ ផ្ទៃខាងក្រោយ) ដើម្បីអនុវត្តទៅលើ View នីមួយៗ ហៅថាអ្វី?**
A. Theme  
B. Theme.AppCompat  
C. Style  
D. Alternative Resource  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៨៖ តើការកំណត់ Style ទាំងឡាយដែលចង់ឱ្យជះឥទ្ធិពលទៅលើ Activity មួយ ឬកម្មវិធីទាំងមូល (Application) ហៅថាអ្វី?**
A. Style  
B. Target SDK  
C. Theme  
D. Gradle Configuration  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៩៖ តើការហៅប្រើប្រាស់ធនធានអក្សរ (String) នៅក្នុងកូដ Java ត្រូវធ្វើឡើងតាមរយៈទម្រង់មួយណា?**
A. `@string/hello`  
B. `R.drawable.hello`  
C. `R.string.hello`  
D. `res.values.strings.hello`  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ១០៖ ដើម្បីឱ្យកម្មវិធីអាចគាំទ្រការប្តូរទៅជាភាសាខ្មែរបាន តើត្រូវបង្កើត فولឌ័រភាសាឈ្មោះអ្វីនៅក្នុង res?**
A. `values-cambodia`  
B. `values-km`  
C. `values-kh`  
D. `values-khmer`  
*   **ចម្លើយត្រឹមត្រូវ៖ C**

---

## ប្រភេទទី ២៖ សំណួរសរសេរ និងពន្យល់ (Structured Questions)

**សំណួរ ១៖** ចូរពន្យល់ពីភាពខុសគ្នារវាង `dp` និង `sp` ព្រមទាំងផ្តល់អនុសាសន៍នៃការប្រើប្រាស់ឯកតានីមួយៗ។
*   **ចម្លើយ៖** 
    *   **dp (density-independent pixels):** ជាឯកតាដែលមិនអាស្រ័យលើដង់ស៊ីតេភីកសែលនៃអេក្រង់ឧបករណ៍ឡើយ។ វាត្រូវបានប្រើសម្រាប់កំណត់ទំហំទទឹង កម្ពស់ គម្លាតខាងក្នុង (padding) ឬគម្លាតខាងក្រៅ (margin) របស់ View។
    *   **sp (scale-independent pixels):** ជាឯកតាដែលប្រែប្រួលទៅតាមចំណូលចិត្តការកំណត់ទំហំអក្សរនៅលើទូរស័ព្ទរបស់អ្នកប្រើប្រាស់។ វាត្រូវបានប្រើសម្រាប់តែកំណត់ទំហំអក្សរ (textSize) ប៉ុណ្ណោះ ដើម្បីកុំឱ្យអក្សរកម្មវិធីរបស់យើងបាត់បង់សោភ័ណភាពពេលអ្នកប្រើប្រាស់ប្តូរទំហំអក្សរក្នុងទូរស័ព្ទ។

**សំណួរ ២៖** ចូររៀបរាប់ពីមុខងារ និងតួនាទីរបស់ឯកសារ `AndroidManifest.xml`។
*   **ចម្លើយ៖** ឯកសារ `AndroidManifest.xml` ដើរតួជាឯកសារស្នូលរបស់កម្មវិធី ដែលមានផ្ទុកនូវរាល់ព័ត៌មានចម្បងៗដូចជា Android Version, សិទ្ធិបញ្ជាឧបករណ៍ (Access Permissions), ព័ត៌មានលម្អិតរបស់កម្មវិធី (Metadata) និងការកំណត់សមាសធាតុផ្សេងៗរបស់ Application។ វាក៏ជាស្ពានដោះស្រាយទំនាក់ទំនងរវាង Android OS ជាមួយនឹងកម្មវិធីផងដែរ។

**សំណួរ ៣៖** ចូរកំណត់ពីភាពខុសគ្នារវាង `drawable folder` និង `mipmap folder`។
*   **ចម្លើយ៖** 
    *   **drawable folder:** ត្រូវបានប្រើសម្រាប់រក្សារាល់រូបភាពទូទៅទាំងអស់ (ដូចជា .png, .jpg, .gif, ឬ shapes) ដែលប្រើប្រាស់ក្នុងការរចនាផ្ទៃ UI របស់កម្មវិធី។
    *   **mipmap folder:** ត្រូវបានប្រើប្រាស់សម្រាប់តែរក្សាទុកនូវរូបតំណាងកម្មវិធី (App / Launcher Icons) ប៉ុណ្ណោះ។ វាមានច្រើនកម្រិតដង់ស៊ីតេអេក្រង់ដើម្បីឱ្យឧបករណ៍ទូរស័ព្ទបង្ហាញរូបតំណាងបានច្បាស់ល្អទៅតាមទំហំអេក្រង់ផ្សេងៗគ្នា។

**សំណួរ ៤៖** តើធនធានប្រភេទ "Alternative Resource" គឺជាអ្វី? ចូរផ្តល់ឧទាហរណ៍។
*   **ចម្លើយ៖** Alternative Resource គឺជាធនធានជំនួសដែលត្រូវបានរចនាឡើងដើម្បីដំណើរការតម្រូវទៅតាមលក្ខខណ្ឌជាក់លាក់របស់ឧបករណ៍ (ដូចជាភាសា តំបន់ ឬទិសដៅបង្វិលអេក្រង់)។
    *   *ឧទាហរណ៍៖* `res/layout-land` ប្រើនៅពេលអេក្រង់ទូរស័ព្ទបង្វិលផ្តេក (Landscape) និង `values-kh` សម្រាប់បង្ហាញអក្សរជាភាសាខ្មែរ។

**សំណួរ ៥៖** ចូរពន្យល់ពីរបៀបអនុវត្ត Style ទៅកាន់ View នៅក្នុង XML និងរបៀបអនុវត្ត Theme ទៅកាន់កម្មវិធីទាំងមូល។
*   **ចម្លើយ៖** 
    *   ដើម្បីអនុវត្ត **Style** ទៅកាន់ View ត្រូវប្រើប្រាស់ Attribute `style` នៅក្នុង Tag View៖ `<TextView style="@style/textViewStyle" ... />`។
    *   ដើម្បីអនុវត្ត **Theme** ទៅកាន់កម្មវិធីទាំងមូល ត្រូវប្រកាសនៅក្នុង Tag `<application>` នៃឯកសារ `AndroidManifest.xml`៖ `<application android:theme="@style/AppTheme" ...>`។

---

## ប្រភេទទី ៣៖ លំហាត់អនុវត្តកូដ (Coding Exercises)

**លំហាត់ ១ (XML Design):** ចូរសរសេរកូដ XML ដើម្បីកំណត់តម្លៃ Style មួយដែលមានឈ្មោះថា `"customButtonStyle"` នៅក្នុងឯកសារ `res/values/styles.xml` ដោយកំណត់ពណ៌អក្សរពណ៌ស (`#ffffff`), ទំហំអក្សរ `18sp` និងកំណត់ទម្រង់អក្សរជាអក្សរធំទាំងអស់ (AllCaps)។
*   **ចម្លើយ៖**
    ```xml
    <resources>
        <style name="customButtonStyle">
            <item name="android:textColor">#ffffff</item>
            <item name="android:textSize">18sp</item>
            <item name="android:textAllCaps">true</item>
        </style>
    </resources>
    ```

**លំហាត់ ២ (Java Code - Resource Accessing):** ចូរសរសេរកូដ Java មួយបន្ទាត់ដើម្បីទាញយកតម្លៃអក្សរពី `strings.xml` ដែលមាន ID `@string/welcome_msg` មកដាក់ក្នុង Variable ប្រភេទ String ឈ្មោះថា `welcomeText`។
*   **ចម្លើយ៖**
    ```java
    String welcomeText = getResources().getString(R.string.welcome_msg);
    ```

**លំហាត់ ៣ (Java Code - Language Change):** ចូរសរសេរកូដ Java បង្កើត Method មួយឈ្មោះថា `changeLanguage(String langCode)` ដើម្បីផ្លាស់ប្តូរភាសារបស់កម្មវិធី Android dynamically។
*   **ចម្លើយ៖**
    ```java
    public void changeLanguage(String langCode) {
        Resources resources = getResources();
        DisplayMetrics dm = resources.getDisplayMetrics();
        Configuration config = resources.getConfiguration();
        config.locale = new Locale(langCode.toLowerCase());
        resources.updateConfiguration(config, dm);
    }
    ```

---
💡 **លោកគ្រូ/អ្នកគ្រូ អាចទាញយករូបភាពតំណាងមេរៀន `android_project_structure_diagram.png` ពីផ្ទាំង Studio Panel ដើម្បីយកទៅប្រើប្រាស់ក្នុងស្លាយបង្ហាញសិស្សបានភ្លាមៗ! តើលោកគ្រូ/អ្នកគ្រូ ចង់ឱ្យខ្ញុំរៀបចំស្លាយមេរៀន (Slide Deck) សម្រាប់ Chapter 2 នេះបន្ថែមទៀតដែរឬទេ?**
