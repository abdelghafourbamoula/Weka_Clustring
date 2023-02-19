
## The PAM Clustering Algorithm in Weka

Class MyPAM, implementation of PAM algorithm
* This class if modified from SimpleKMeans.java, which is the
* implementation of K-Means clustering algorithm in the WEKA system.

> **Note**
> 
> the application shoud runing in weka gui chooser in `weka.gui.GUIChooser`
> then loading the class MyPAM on weka clustrer

#### Dependencies

`JDK 17`
```xml
<dependency>
    <groupId>nz.ac.waikato.cms.weka</groupId>
    <artifactId>optics_dbScan</artifactId>
    <version>1.0.3</version>
</dependency>
```
or `weka.jar` file

#### run
```java
 public static void main (String[] argv) throws Exception {
        runClusterer(new MyPAM(), argv);

        BufferedReader breader = null;
        breader = new BufferedReader(new FileReader("path_to\resources\\data\\pam_big.arff"));
        Instances Train = new Instances(breader);
        //Train.setClassIndex(Train.numAttributes() - 1); // comment out this line
        MyPAM pam = new MyPAM();
        pam.setNumClusters(3);
        pam.buildClusterer(Train);
        System.out.println(pam);
        System.out.println("- max iter: "+pam.getMaxIterations());
        System.out.println("- revision: "+pam.getRevision());
        breader.close();
    }
```
---

![java](https://badgen.net/badge/Java/17/red?icon=java) 
![intellij](https://img.shields.io/static/v1?label=IntelliJ%20IDEA%20&message=2022.2.3&color=white&logo=intellijidea)
![weka](https://img.shields.io/static/v1?label=Weka&message=3.8.6&color=red&logo=waikato)