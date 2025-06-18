## 1.  How do you create a jenkins job to build a maven project from a github repo ?

**Answer**

    - **Step 1:**Open jenkins and click on "new item"
    - **step 2:** Enter a name for the job and select "Freestyle project", Then click "OK".
    - **Step 3:** In the "SOurce code management" Section, select "Git" and enter the repo url.
    - **step 4:** In the "build Triggers" section, choose "Github Hook trigger for thr GITScm pullling."
    - **Step 5"** In the "Build" section, click "add build step" and select "invoke top-level maven targets."
    - **step 6:** In the "Goals" Field, enter `clean install`.
    - **Step 7:** Save the job and click "Build Now" to test it.
