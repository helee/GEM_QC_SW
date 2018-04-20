# GEM_QC2_Long

## Authors
Inseok Yoon: inseok.yoon@cern.ch
Haneol Lee: haneol.lee@cern.ch

## Install CAEN CAENHVWrapper library
CAEN CAENHVWrapper library is necessary. To download it, please refer http://www.caen.it/csite/CaenProd.jsp?parent=43&idmod=835# Then you need to uncompress tar file, and install the library. To install, go to directory where the library is uncompressed. Then type
<pre>
sudo ./install.sh
</pre>

## Compile HV control codes
<pre>
git clone git@github.com:diracyoon/GEM_QC_SW
cd GEM_QC_SW/Code/Server
make
cd ../Client
make
</pre>
Excutables shoud appear.

## Usage
# Running server
You shoud get su right first because CAEN wrapper library needs it. Then the environmental variables shuld be set. Now you are OK to run server. If the process is failed due to communication to HV module, just try to run one more time.
<pre>
sudo -s
cd Macro
source Env.sh
./Run_Server.sh
</pre>
# Running client
Prepare other terminal. You need su right again. The environmental variables are needed again. Then you are OK to run client. Run_Client will ask foil id, HV channel number, relative humidity, temperaure and your name. 
<pre>
sudo -s
cd Macro
source Env.sh
./Run_Client.sh
input foil id, channel number  
</pev>
If the server is not running or owned HV channel by other channel process, Run_Client.sh scrip will notice and kill itself.
