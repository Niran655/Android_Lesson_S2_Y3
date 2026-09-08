#Chapter 1: Getting started with android
## ផ្នែកទី ១៖ ខ្លឹមសារមេរៀនលម្អិត (Lesson Contents)

### ១. និយមន័យគ្រឹះនៃ Android
*   **Android:** គឺជាប្រព័ន្ធប្រតិបត្តិការ (Operating System) និងជាគំរូភាសា (Programming Platform) ដែលត្រូវបានអភិវឌ្ឍឡើងដោយ**ក្រុមហ៊ុន Google** សម្រាប់ដំណើរការនៅលើទូរស័ព្ទដៃ និងឧបករណ៍ចល័តផ្សេងៗទៀត ដូចជាថេបប្លែត (Tablets) ជាដើម។ វាអាចដំណើរការនៅលើឧបករណ៍ផ្សេងៗគ្នាជាច្រើនដែលផលិតដោយក្រុមហ៊ុនផ្សេងៗគ្នា លើកលែងតែផលិតផលរបស់ Apple។
*   **ជំនាន់នៃ Android (Android Versions):** ប្រព័ន្ធប្រតិបត្តិការ Android ត្រូវបានបោះពុម្ពផ្សាយ (Publish) ទៅតាមជំនាន់ផ្សេងៗគ្នាជាច្រើន ចាប់តាំងពី **Apple Pie 1.0** នៅក្នុងឆ្នាំ ២០០៨ រហូតដល់ **Android 15 (Vanilla Ice Cream)** ដែលចេញផ្សាយនៅថ្ងៃទី ៣ ខែកញ្ញា ឆ្នាំ ២០២៤។

### ២. ឧបករណ៍អភិវឌ្ឍន៍កម្មវិធី Android (Android Development Tools)
ដើម្បីបង្កើតកម្មវិធី Android (Android App) អ្នកអភិវឌ្ឍន៍ត្រូវដំឡើងកម្មវិធី និងឧបករណ៍ចាំបាច់ដូចខាងក្រោម៖
*   **Android Studio (IDE):** ជាកម្មវិធីចម្បងដែលប្រើប្រាស់សម្រាប់សរសេរកូដ និងបង្កើត Graphic User Interface (GUI)។
*   **Android Software Development Kit (Android SDK):** រួមបញ្ចូលនូវបណ្តុំ Software និងឧបករណ៍ដែលជួយសម្រួលដល់អ្នកសរសេរកូដដើម (Source Code) និងគ្រប់គ្រងឧបករណ៍។
*   **Android Debug Bridge (ADB):** ជាឧបករណ៍មួយដែលមាននៅក្នុង Android SDK ដែលអនុញ្ញាតឱ្យយើងគ្រប់គ្រងឧបករណ៍ (Device)។
*   **Gradle Tools:** ជាឧបករណ៍ចាំបាច់ដែលត្រូវតែមាន សម្រាប់ធ្វើការបំលែង បង្កើត និងចងក្រង (Compile) ឯកសារកូដ និង Resource ផ្សេងៗ ទៅជាកញ្ចប់កម្មវិធី (Package), ការដាក់ពង្រាយ (Deploy) និងដំណើរការសាកល្បងកម្មវិធី។
*   **Virtual Device (Emulator) ឬ Real Device:** ប្រើសម្រាប់ដំណើរការសាកល្បងកម្មវិធីដែលបានបង្កើតឡើង។ Emulator គឺជាឧបករណ៍និម្មិតដែលបង្កើតឡើងនៅលើ Android Studio។

### ៣. តម្រូវការប្រព័ន្ធសម្រាប់ការដំឡើង (System Requirements)
ដើម្បីដំឡើង និងដំណើរការ Android Studio បានរលូន កុំព្យូទ័រត្រូវមានលក្ខណៈសម្បត្តិដូចខាងក្រោម៖
*   **ប្រព័ន្ធប្រតិបត្តិការ:** Microsoft Windows XP ឬជំនាន់ក្រោយ, Mac OS X 10.5.8 ឬជំនាន់ក្រោយ (ជាមួយ Intel chip), ឬ Linux (រួមទាំង GNU C Library 2.7 ឬជំនាន់ក្រោយ)។
*   **RAM:** យ៉ាងហោចណាស់ **4 GB** (ណែនាំ **8 GB RAM** ឡើងទៅ និងបូកបន្ថែម 1 GB សម្រាប់ដំណើរការ Emulator)។
*   **ទំហំផ្ទុក (Free Storage Space):** យ៉ាងហោចណាស់ **2 GB** (ណែនាំ **4 GB** ឡើងទៅ ដោយក្នុងនោះ 500 MB សម្រាប់ IDE និង 1.5 GB សម្រាប់ Android SDK និង Emulator system image)។
*   **កម្រិតបង្ហាញអេក្រង់ (Screen Resolution):** យ៉ាងហោចណាស់ **1280 x 800**។

### ៤. រចនាសម្ព័ន្ធរបស់ Android (Android Architecture)
រចនាសម្ព័ន្ធរបស់ Android ត្រូវបានបែងចែកជា ៥ ស្រទាប់ចម្បងៗ ចាប់ពីស្រទាប់ Kernel រហូតដល់កម្មវិធីដែលអ្នកប្រើប្រាស់អាចប្រកៀកប្រកិតបាន រួមមាន៖
1.  **System Apps:** មានផ្ទុកនូវកម្មវិធីផ្សេងៗដូចជា Browser, Camera, Gallery, Music និង Phone។
2.  **Java API Framework (Application Framework):** ជា API ដែលអនុញ្ញាតឱ្យមានអន្តរកម្មកម្រិតខ្ពស់ (high-level interactions) ជាមួយនឹងប្រព័ន្ធ Android។
3.  **Libraries and Runtime (Native C/C++ Libraries - Android Runtime):** គឺជាបណ្ណាល័យសម្រាប់មុខងារ Framework ទូទៅជាច្រើន (ដូចជា graphic rendering, data storage, web browsing) និងមាន Core Java Libraries សម្រាប់ដំណើរការកម្មវិធី Android។
4.  **Hardware Abstraction Layer (HAL):** ជាស្រទាប់សម្របសម្រួលផ្នែក Hardware។
5.  **Linux Kernel:** ជាស្រទាប់ទំនាក់ទំនងសម្រាប់ទ្រទ្រង់ Hardware ខាងក្រោម (Drivers - Power Management)។

### ៥. សមាសធាតុនៃកម្មវិធី (Application Components)
គឺជាបណ្តុំសមាសធាតុសំខាន់នៃកម្មវិធី Android ដែលត្រូវបានផ្គុំគ្នានៅក្នុងឯកសារ **`AndroidManifest.xml`** ដើម្បីកំណត់ពីសមាសធាតុនីមួយៗ និងរបៀបដែលពួកវាមានទំនាក់ទំនងគ្នា។ សមាសធាតុសំខាន់ៗទាំងនោះមាន ៤ គឺ៖
*   **Activities:** ប្រើសម្រាប់កំណត់ UI និងគ្រប់គ្រងអន្តរកម្មរបស់អ្នកប្រើប្រាស់ទៅលើអេក្រង់ទូរស័ព្ទ។
*   **Services:** ប្រើសម្រាប់គ្រប់គ្រងដំណើរការផ្ទៃខាងក្រោយ (Background processing) ដែលទាក់ទងនឹងកម្មវិធី។
*   **Broadcast Receivers:** ប្រើសម្រាប់គ្រប់គ្រងទំនាក់ទំនងរវាងប្រព័ន្ធប្រតិបត្តិការ Android និងកម្មវិធី។
*   **Content Providers:** ប្រើសម្រាប់គ្រប់គ្រងទិន្នន័យ និងដោះស្រាយបញ្ហាទិន្នន័យ។

### ៦. ជំនាញដែលត្រូវការដើម្បីក្លាយជាអ្នកអភិវឌ្ឍន៍ (Android Developer)
*   **Native Android App Developer:** ត្រូវមានចំណេះដឹងទាក់ទងនឹងភាសា **Java** ឬ **Kotlin**។
*   **Cross Platform App Developer:** ត្រូវមានចំណេះដឹងទាក់ទងនឹង **React Native, Ionic,** ឬ **Flutter**។

---

## ផ្នែកទី ២៖ កម្រងសំណួរសម្រាប់ប្រឡង (Exam Questions)

## ប្រភេទទី ១៖ សំណួរជ្រើសរើសចម្លើយ (Multiple Choice Questions)

**សំណួរ ១៖ តើក្រុមហ៊ុនមួយណាដែលបានអភិវឌ្ឍប្រព័ន្ធប្រតិបត្តិការ Android?**
A. Apple  
B. Microsoft  
C. Google  
D. Samsung  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយមេរៀន៖ "...អភិវឌ្ឍដោយក្រុមហ៊ុន Google...")។

**សំណួរ ២៖ តើ Android ជំនាន់ដំបូង (1.0) ដែលចេញផ្សាយនៅឆ្នាំ ២០០៨ មានឈ្មោះថាអ្វី?**
A. Astro  
B. Cupcake  
C. Apple Pie  
D. Banana Bread  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយមេរៀន៖ "...ចាប់ពី Apple Pie 1.0 (២០០៨)...")។

**សំណួរ ៣៖ តើមួយណាជាឧបករណ៍ដែលមានតួនាទីក្នុងការបំលែង ចងក្រង (Compile) កញ្ចប់ (Package) និងដាក់ពង្រាយ (Deploy) កម្មវិធី Android?**
A. Android Studio IDE  
B. Gradle Tools  
C. Java API Framework  
D. HAL  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយមេរៀន៖ "Gradle Tools... ចងក្រង (Compile) កញ្ចប់ (Package) ដាក់ពង្រាយ (Deploy) និងចាប់ផ្តើមកម្មវិធី...")។

**សំណួរ ៤៖ តើទំហំ RAM អប្បបរមា (Minimum) ប៉ុន្មានដែលតម្រូវការសម្រាប់ការអភិវឌ្ឍកម្មវិធី Android Studio?**
A. 2 GB  
B. 4 GB  
C. 8 GB  
D. 16 GB  
*   **ចម្លើយត្រឹមត្រូវ៖ B** (យោងតាមស្លាយមេរៀន៖ "4 GB RAM is required at least...")។

**សំណួរ ៥៖ តើរចនាសម្ព័ន្ធរបស់ Android (Android Architecture) ត្រូវបានបែងចែកជាប៉ុន្មានស្រទាប់ (Layers) ចម្បង?**
A. ៣ ស្រទាប់  
B. ៤ ស្រទាប់  
C. ៥ ស្រទាប់  
D. ៦ ស្រទាប់  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយមេរៀន៖ "...ដែលត្រូវបានបែងចែកជា ៥ ស្រទាប់ចម្បងៗ...")

**សំណួរ ៦៖ តើឯកសារមួយណាដែលប្រើសម្រាប់កំណត់សមាសធាតុសំខាន់ៗនៃកម្មវិធី (Application Components) និងទំនាក់ទំនងរវាងពួកវា?**
A. build.gradle  
B. MainActivity.java  
C. AndroidManifest.xml  
D. activity_main.xml  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយមេរៀន៖ "...ដែលត្រូវបានផ្គុំនៅក្នុង AndroidManifest.xml...")។

**សំណួរ ៧៖ តើសមាសធាតុ (Component) មួយណាដែលប្រើសម្រាប់កំណត់ UI និងគ្រប់គ្រងអន្តរកម្មរបស់អ្នកប្រើប្រាស់នៅលើអេក្រង់ទូរស័ព្ទ?**
A. Services  
B. Broadcast Receivers  
C. Content Providers  
D. Activities  
*   **ចម្លើយត្រឹមត្រូវ៖ D** (យោងតាមស្លាយមេរៀន៖ "Activities៖ គឺត្រូវបានប្រើសម្រាប់កំណត់ UI និងគ្រប់គ្រងអន្តរកម្មរបស់អ្នកប្រើប្រាស់...")។

**សំណួរ ៨៖ ប្រសិនបើអ្នកចង់អភិវឌ្ឍកម្មវិធីបែប Cross-Platform តើអ្នកគួរប្រើប្រាស់ Framework មួយណា?**
A. Java / Kotlin  
B. Android Studio SDK  
C. React Native / Ionic / Flutter  
D. Linux Kernel  
*   **ចម្លើយត្រឹមត្រូវ៖ C** (យោងតាមស្លាយមេរៀន៖ "...ReactNative/ Ionic/ Flutter for Cross Platform App")។

---

## ប្រភេទទី ២៖ សំណួរសរសេរ និងពន្យល់ (Structured Questions)

**សំណួរ ១៖** ចូរពន្យល់ពីតួនាទីរបស់ **Android SDK** និង **Android Studio** នៅក្នុងការអភិវឌ្ឍកម្មវិធី Android។
*   **ចម្លើយ៖**
    *   **Android Studio:** គឺជាកម្មវិធីអភិវឌ្ឍន៍ (IDE) សម្រាប់សរសេរកូដ និងបង្កើត Graphic User Interface (GUI) នៃកម្មវិធី។
    *   **Android SDK (Software Development Kit):** គឺជាបណ្តុំឧបករណ៍ និងបណ្ណាល័យដែលជួយឱ្យអ្នកអភិវឌ្ឍន៍សរសេរកូដដើម និងគ្រប់គ្រងឧបករណ៍ Android។

**សំណួរ ២៖** ចូររៀបរាប់ពីសមាសធាតុសំខាន់ៗទាំង ៤ នៃកម្មវិធី Android (Application Components) និងពន្យល់ពីតួនាទីសង្ខេបរបស់សមាសធាតុនីមួយៗ។
*   **ចម្លើយ៖** សមាសធាតុសំខាន់ៗទាំង ៤ រួមមាន៖
    1.  **Activities:** កំណត់ UI និងគ្រប់គ្រងអន្តរកម្មរបស់អ្នកប្រើប្រាស់នៅលើអេក្រង់ទូរស័ព្ទ។
    2.  **Services:** គ្រប់គ្រងដំណើរការផ្ទៃខាងក្រោយ (Background process)។
    3.  **Broadcast Receivers:** គ្រប់គ្រងការប្រាស្រ័យទាក់ទងរវាងប្រព័ន្ធប្រតិបត្តិការ Android និងកម្មវិធី។
    4.  **Content Providers:** គ្រប់គ្រងទិន្នន័យ និងដោះស្រាយបញ្ហាទិន្នន័យ។

**សំណួរ ៣៖** តើជំហានសំខាន់ៗក្នុងការរៀបចំដំឡើង Android Studio នៅលើកុំព្យូទ័រមានអ្វីខ្លះ?
*   **ចម្លើយ៖** ជំហានសំខាន់ៗរួមមាន៖
    1.  ទាញយក និងដំឡើង JDK និងកំណត់ Environment “`JAVA_HOME`”។
    2.  ទាញយក Android Studio IDE និងដំឡើងតាមរយៈ Wizard។
    3.  បង្កើតឧបករណ៍និម្មិត (Virtual Device or Emulator) ជាមួយ Android Studio។
    4.  ត្រូវមានការតភ្ជាប់អ៊ីនធឺណិត (Internet Connection) ក្នុងពេលដំឡើង និងរៀបចំ។


