# Android_Lesson_S2_Y3

# មេរៀនទី ១៖ ការចាប់ផ្តើមជាមួយនឹង Android (Chapter 1: Getting Started with Android)

## ១. និយមន័យ និងសមាសធាតុសំខាន់ៗ (Key Definitions & Concepts)

* **Android**: គឺជាប្រព័ន្ធប្រតិបត្តិការ (Operating System) និងជាគំរូភាសា (Programming Platform) ដែលត្រូវបានអភិវឌ្ឍដោយក្រុមហ៊ុន Google សម្រាប់ដំណើរការលើទូរស័ព្ទដៃ និងឧបករណ៍ចល័តផ្សេងៗ (ដូចជា Tablets)។


* **រចនាសម្ព័ន្ធ Android (Android Architecture Layers)**: មាន ៥ ស្រទាប់ចម្បង៖
1. **System Apps**: កម្មវិធីស្រាប់ដែលមានក្នុងប្រព័ន្ធ ដូចជា Phone, Browser, Camera។
2. **Java API Framework**: ស្រទាប់ផ្តល់ API សម្រាប់ទំនាក់ទំនងកម្រិតខ្ពស់ជាមួយប្រព័ន្ធ Android។
3. **Native C/C++ Libraries & Android Runtime (ART)**: បណ្ដុំ Libraries សម្រាប់ដំណើរការ Graphics, Data Storage, Web browsing និង Core Java libraries។
4. **Hardware Abstraction Layer (HAL)**: ស្រទាប់តភ្ជាប់រវាង Hardware Drivers និង Framework។
5. **Linux Kernel**: ស្រទាប់បាតក្រោមគេ សម្រាប់គ្រប់គ្រង Drivers (Power, Camera, Display, Bluetooth, Memory)។


* **សមាសធាតុនៃកម្មវិធី (Application Components)**: មាន ៤ យ៉ាងសំខាន់ៗ៖
1. **Activities**: ប្រើសម្រាប់រចនា / កំណត់ UI និងគ្រប់គ្រងអន្តរកម្មរបស់អ្នកប្រើប្រាស់នៅលើអេក្រង់។


2. **Services**: ប្រើសម្រាប់គ្រប់គ្រងដំណើរការ Background (ផ្ទៃខាងក្រោយ)។
3. **Broadcast Receivers**: គ្រប់គ្រងទំនាក់ទំនងរវាងប្រព័ន្ធប្រតិបត្តិការ Android និង Application។
4. **Content Providers**: គ្រប់គ្រងទិន្នន័យ និងដោះស្រាយបញ្ហា Database របស់កម្មវិធី។



---

## ២. ឧបករណ៍ និងភាសាដែលប្រើប្រាស់ (Tools & Technologies Used)

* **Android Studio**: កម្មវិធី IDE ចម្បងសម្រាប់សរសេរកូដ រចនា GUI និងអភិវឌ្ឍ Android App។


* **Android SDK (Software Development Kit)**: បណ្ដុំឧបករណ៍ចាំបាច់សម្រាប់ Compile, Package និង Deploy កម្មវិធី។ រួមមាន **ADB (Android Debug Bridge)** សម្រាប់គ្រប់គ្រង ឬដោះស្រាយកំហុស (Debug) លើ Virtual Device ឬ Real Device។


* **Gradle Tools**: ឧបករណ៍សម្រាប់ Compile និង Build Project។
* **Emulator / Virtual Device**: ឧបករណ៍និម្មិតនៅលើកុំព្យូទ័រសម្រាប់សាកល្បងដំណើរការ App។


* **ភាសាសរសេរកូដ (Programming Languages & Frameworks)**៖
* **Native App Development**: Java ឬ Kotlin
* **Cross-Platform App Development**: React Native, Flutter, ឬ Ionic
* **UI Structure**: XML ប្រើសម្រាប់រចនា giao diện (UI Design)



---

## ៣. គំរូសំណួរ និងចម្លើយសម្រាប់ប្រឡង (Exam Questions & Answer Key)

### ផ្នែកទី ១៖ សំណួរជ្រើសរើសចម្លើយត្រឹមត្រូវ (Multiple Choice Questions)

**សំណួរទី ១៖** តើប្រព័ន្ធប្រតិបត្តិការ Android ត្រូវបានអភិវឌ្ឍឡើងដោយក្រុមហ៊ុនមួយណា?

A. Apple

B. Microsoft

C. Google

D. Samsung

> **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរទី ២៖** តើសមាសភាគ (Application Component) មួយណាដែលទទួលខុសត្រូវលើការបង្ហាញ Graphic User Interface (GUI) និងទទួលអន្តរកម្មពីអ្នកប្រើប្រាស់?

A. Services

B. Activities

C. Content Providers

D. Broadcast Receivers

> **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរទី ៣៖** តើឧបករណ៍ ADB នៅក្នុង Android SDK មានឈ្មោះពេញថាតាម៉េច?

A. Android Data Base

B. Android Debug Bridge

C. Android Deployment Base

D. Android Device Builder

> **ចម្លើយត្រឹមត្រូវ៖ B**

---

### ផ្នែកទី ២៖ សំណួរស្រាវជ្រាវ និងពន្យល់ (Short Answer & Essay Questions)

**សំណួរទី ៤៖** ចូរបរិយាយពីសមាសភាគសំខាន់ទាំង ៤ (4 Application Components) របស់ Android Applications ឲ្យបានច្បាស់លាស់។

* **ចម្លើយ៖** ត្រូវរៀបរាប់ពី Activity, Service, Broadcast Receiver, និង Content Provider ព្រមទាំងតួនាទីរបស់ពួកវានីមួយៗ។

**សំណួរទី ៥៖** ប្រសិនបើអ្នកចង់ក្លាយជា Native Android Developer តើអ្នកគួរសិក្សាភាសាសរសេរកូដ (Programming Languages) អ្វីខ្លះ? ហើយប្រសិនបើចង់ធ្វើជា Cross-Platform Developer តើត្រូវប្រើ Framework អ្វីខ្លះ?

* **ចម្លើយ៖**
* **Native:** Java ឬ Kotlin
* **Cross-Platform:** React Native, Flutter, ឬ Ionic

