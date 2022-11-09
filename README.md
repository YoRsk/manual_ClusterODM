# ClusterODM-manual
for Windows system
## Github
[WebODM](https://github.com/OpenDroneMap/WebODM/)  
[ClusterODM](https://github.com/OpenDroneMap/ClusterODM)  
[Distributed split-merge](https://docs.opendronemap.org/large/?highlight=distributed#getting-started-with-distributed-split-merge)  
https://www.opendronemap.org/clusterodm/  
## Prepare beforehand 事前准备
### Download
#### 1 Cluster Host
1.[Docker.exe](https://www.docker.com/)  
2.[ODM.exe](https://github.com/OpenDroneMap/ODM/releases)  
3.[ClusterODM.exe](https://github.com/OpenDroneMap/ClusterODM/releases/tag/v1.5.3)  
4.[NodeODM.exe](https://github.com/OpenDroneMap/NodeODM/releases) (optional)  
5.WebODM  
> enable Docker.exe -> Git Bash -> `git clone https://github.com/OpenDroneMap/WebODM --config core.autocrlf=input --depth 1`  
  
  
#### 2 Node 
1.[ODM.exe](https://github.com/OpenDroneMap/ODM/releases)   
2.[NodeODM.exe](https://github.com/OpenDroneMap/NodeODM/releases)  
  
  
## Enable softwares
### 1 Cluster Host
#### 1. clusterodm.exe  
![](https://github.com/YoRsk/ClusterODM-manual/blob/main/images/cluster1.png)  
  
Win + R -> cmd -> ``` telnet localhost 8080 ```
>if INVALID when you input
>Escape ( *'ctrl+]'* or *'^]'* ) -> ```send COMMAND ``` -> Enter twice
>![](https://github.com/YoRsk/ClusterODM-manual/blob/main/images/telnet1.png)  
  
  
#### 2. webodm  
enable docker.exe-> Git Bash -> 
```
cd WebODM
./webodm.sh start --default-nodes 0
```
-> http://localhost:8000  
> remember your account please  
  
#### 3. nodeodm(optional)
>same as below,but the nodeodm port maybe is 3001 now,because port 3000 is occupied by clusterodm.  
  
  
### 2 Node
Win + R -> cmd -> ``` cd NODEODM'S CATEGORY``` -> ``` nodeodm.exe --odm_path ODM'S CATEGORY ```  
![](https://github.com/YoRsk/ClusterODM-manual/blob/main/images/node1.png)  

## Operations in Cluster Host
### telnet
```send NODE ADD <node-odm-ip-1> 3000 ```
```
$ telnet <cluster-odm-ip> 8080
Connected to <cluster-odm-ip>.
Escape character is '^]'.
[...]
# node add <node-odm-ip-1> 3000
# node add <node-odm-ip-2> 3000
# node add <node-odm-in cluster host-ip-3> 3001
[...]
# node list
1) <node-odm-ip-1>:3000 [online] [0/2] <version 1.5.1>
2) <node-odm-ip-2>:3000 [online] [0/2] <version 1.5.1>
3) <node-odm-in cluster host-ip-3>:3000 [online] [0/2] <version 1.5.1>
```
> ip: win + R ->cmd -> ipconfig  
> *All machines must be on one LAN*
>  
### webodm
#### 1. add node (both NodeODMs and ClusterODM)
1.input NodeODM ip and port  
![](https://github.com/YoRsk/ClusterODM-manual/blob/main/images/webodmnote1.png)  
  
2.input ClusterODM ip and port  
![](https://github.com/YoRsk/ClusterODM-manual/blob/main/images/webodmcluster1.png)  
  
  
#### 2. start Mission
> Mission's parameter  
> processing node : cluster-odm-ip:port (3000 or others)  
> sm-cluster http://cluster-odm-ip:port  
  
  
Such as
![](https://github.com/YoRsk/ClusterODM-manual/blob/main/images/webodmmission1.png)
