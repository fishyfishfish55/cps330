# Introduction <!-- 1 min -->
- Project: Building a network Intrusion Detection System (IDS) <!-- what is an IDS>
- Found many examples <!-- see kaggle, google, etc. MAchine learning is industry standard>
- Dataset: [UNSW-NB15 dataset](https://research.unsw.edu.au/projects/unsw-nb15-dataset) <!-- >
    - Moustafa, Nour, and Jill Slay. "UNSW-NB15: a comprehensive data set for network intrusion detection systems (UNSW-NB15 network data set)."Military Communications and Information Systems Conference (MilCIS), 2015. IEEE, 2015.
    - Moustafa, Nour, and Jill Slay. "The evaluation of Network Anomaly Detection Systems: Statistical analysis of the UNSW-NB15 data set and the comparison with the KDD99 data set." Information Security Journal: A Global Perspective (2016): 1-14.
- Paper: ["Network Intrusion Detection System using Deep Learning"](https://doi.org/10.1016/j.procs.2021.05.025) <!-- Goes through the steps of creating an ANN for IDS purposes>
# Explaination <!-- 2 min -->
## Detection methods
- Signature-based
    - Straightforward approach
    - Misses unknown attacks, requiring constant updating
- Anomaly-based 
    - Detects unknown attacks
    - Produces false positives at unusual, but not malicious, network usage
- Stateful protocol analysis
    - Sees patterns other methods have trouble detecting
    - High resource consumption due to maintaining state information
- Neural Network 
    - Finding unpredictable patterns in lots of complex data - the perfect application!
## CNN vs other ANNs
- CNN allows for finding more complex pattern compared with a fully-connected model
# Implementation <!-- 2-3 min -->
- Local notebook, developed on our very own malachi (containing an NVIDIA Quadro)
```
            .-/+oossssoo+\-.               levi.lacoss@malachi 
        ´:+ssssssssssssssssss+:`           ------------------- 
      -+ssssssssssssssssssyyssss+-         OS: Ubuntu 20.04.6 LTS x86_64 
    .ossssssssssssssssssdMMMNysssso.       Host: Dell Inc. 01NP3N 
   /ssssssssssshdmmNNmmyNMMMMhssssss\      Kernel: 5.15.0-125-generic 
  +ssssssssshmydMMMMMMMNddddyssssssss+     Uptime: 4 days, 23 hours, 45 mins 
 /sssssssshNMMMyhhyyyyhmNMMMNhssssssss\    Packages: 2611 (dpkg), 10 (snap) 
.ssssssssdMMMNhsssssssssshNMMMdssssssss.   Shell: bash 5.0.17 
+sssshhhyNMMNyssssssssssssyNMMMysssssss+   Resolution: 1080x1920, 1920x1080 
ossyNMMMNyMMhsssssssssssssshmmmhssssssso   DE: GNOME 3.36.9 
ossyNMMMNyMMhsssssssssssssshmmmhssssssso   WM: Mutter 
+sssshhhyNMMNyssssssssssssyNMMMysssssss+   WM Theme: Adwaita 
.ssssssssdMMMNhsssssssssshNMMMdssssssss.   Theme: Yaru-dark [GTK2/3] 
 \sssssssshNMMMyhhyyyyhdNMMMNhssssssss/    Icons: Yaru [GTK2/3] 
  +sssssssssdmydMMMMMMMMddddyssssssss+     Terminal: kitty 
   \ssssssssssshdmNNNNmyNMMMMhssssss/      Terminal Font: monospace 9.0 
    .ossssssssssssssssssdMMMNysssso.       CPU: Intel i7-10700 (16) @ 4.800GHz 
      -+sssssssssssssssssyyyssss+-         GPU: NVIDIA Quadro P1000 
        `:+ssssssssssssssssss+:`           GPU: Intel Device 9bc5 
            .-\+oossssoo+/-.               Memory: 5822MiB / 15701MiB 
                                           GPU Driver: Dell Device [1028:09f6] 
                                           Disk (/): 77G / 468G (18%) 
                                           Font: Ubuntu 11 [GTK2/3] 
                                           Local IP: 10.100.150.69 
                                           Public IP: 50.227.112.186 
                                           Users: levi.lacoss 
                                           Locale: en_US.UTF-8
```
- someone turned him off during the break >:(
## Data Exploration
### Explain categories
## Network Results
### Weaknesses
### Strenths
# Conclusion <!-- 1 min -->