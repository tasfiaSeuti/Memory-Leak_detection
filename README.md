# Memory-Leak_detection

This is an Android Application made using Android Studio for teh demonstration of Memory Leak in Android Apps using Android Profiler. 

### Description

### Memory Leak and Crash
1. In this app, There are two activities, i.e. Main activity consists of a button, clicking which opes a new activity "Leaking Activity"
2. We created a GlobalSingleton Interface, which is implemented by other classes to recieve events
3. In this GlobalSingleton, we can register/unregister listeners(these listeners can be adde3d or removed)
4. The Leaking Activity impletemts the GlobalSingleton interface and registers the listener in onStart() but never never unregisters it
5. Now if we see the android profiler, we find that there is memory leak by clicking on Memory lane
(Memory lane shows how much memory is allocated for different categories liuke java, native etc)
6. Whe4n we start the Leaking activity, we see the memory is allocated but when we destroy the activity, if we search, we will find the memory is still allocated, hence Memory Leak is happening
7. As a result of this, If er keep doing this few more times, the app will eventually crash

### Solution
If we go back and unregister the registered listener on the Leaking Activity and run the operations again, we will dind that the memory leak problem has benn solved.

### Programming Language: Kotlin

### Markup Language: XML

### Here the Introduction to Memory Leak Presentation slides/pdf are attached
[MemoryLeakinAndroid.pptx](https://github.com/tasfiaSeuti/Memory-Leak_detection/files/9438513/MemoryLeakinAndroid.pptx)
[Memory Leak in Android- Tasfia Seuti.pptx.pdf](https://github.com/tasfiaSeuti/Memory-Leak_detection/files/9438514/Memory.Leak.in.Android-.Tasfia.Seuti.pptx.pdf)


### Sreenshots

### Android Profiler: Leaking Activity Memory Allocation and No Deallocation
![Screenshot 2022-08-28 at 12 50 13 AM](https://user-images.githubusercontent.com/31209824/187044120-5c0e44f4-3fae-4770-a63b-7ea1478c88a9.png)

### App
![Screenshot 2022-08-28 at 12 35 18 AM](https://user-images.githubusercontent.com/31209824/187044139-dc177692-178d-4edc-bbff-f857c7d57d4c.png)
![Screenshot 2022-08-28 at 12 35 31 AM](https://user-images.githubusercontent.com/31209824/187044140-b7101133-6afe-4009-b8c0-08762f3cdcb8.png)
