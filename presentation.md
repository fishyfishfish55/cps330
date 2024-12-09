# Introduction <!-- 1 min -->
- Project: Building a network Intrusion Detection System (IDS) <!-- what is an IDS-->
    - Started with the idea of building a demo application; reduced scope to a notebook
    - An intrusion detection system is a device or software application that monitors a network or systems for malicious activity or policy violations. Any intrusion activity or violation is typically either reported to an administrator or collected centrally using a security information and event management system. [Wikipedia](https://en.wikipedia.org/wiki/Intrusion_detection_system)
    - Some systems respond automatically
- Found many examples
    - see kaggle, google, etc. 
    - Machine learning is industry standard for IDS
- Bit off a trifle more than I could chew
- Dataset: [UNSW-NB15 dataset](https://research.unsw.edu.au/projects/unsw-nb15-dataset)
    - Moustafa, Nour, and Jill Slay. "UNSW-NB15: a comprehensive data set for network intrusion detection systems (UNSW-NB15 network data set)."Military Communications and Information Systems Conference (MilCIS), 2015. IEEE, 2015.
    - Moustafa, Nour, and Jill Slay. "The evaluation of Network Anomaly Detection Systems: Statistical analysis of the UNSW-NB15 data set and the comparison with the KDD99 data set." Information Security Journal: A Global Perspective (2016): 1-14.
    - This is designed as a successor to the popular KDD98, KDDCUP99 and NSLKDD datasets, and better reflects the state of network attacks in the 2010's
- Paper: ["Network Intrusion Detection System using Deep Learning"](https://doi.org/10.1016/j.procs.2021.05.025)
    - Goes through the steps of creating an ANN for IDS purposes
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
- Local notebook, developed on our very own malachi (containing a better GPU than my laptop)
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
- Zephaniah has a better GPU, which I'm planning to use to actually train the network
## Import data
### Categories
- training_set / testing_set
- `NUSW-NB15_features.csv`
    - A bit of a timesink
    - Had nonexistant features
    - Be careful on datasets with large amounts of features
### Data cleaning / Feature engineering
- Services were `-` not `None`
- Some features highly correlated
## Network Results
- Paper reported 97% to 99%(!) accuracy rate for convolutional network
### Adventures in Convolutional Neural Networks
- I attempted to create a 1-dimensional Convolutional Neural Network for packet classification
- Such an network would have used a 3-dimensional dataset of data _over time_
- While such time data was reported in `NUSW-NB15_features.csv`, it was not present in either the training or the testing datasets 😭
- I would have reshaped the dataset around the timeframe data

# Takeaways <!-- 1 min -->
- Don't get stuck on little things!
    - Technical explorations could have been more connected
- Convolutional neural networks are an extremely powerful tool
- Networks and packets are complecated beasts