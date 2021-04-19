# AIQ_Workload_classification
The pourpose of this playbooks is to allow users to perform bulk updates of performance and efficiancies configurations vi AIQUM. 
<b>Warning bulk updates could cause unexpected performance issues related to scanning of efficancies and incorrect workload identification.</b> 
This repo allows users to input a CSV file with desired workload levels and sets them within NetApp activeIQ Via api calls. 

The following steps are requires to setup the ansible play for execution.<br>

On the ansible instance:<br>
Clone the repo Ansible-with-Active-IQ-Unified-Manager and the play<br>
<b><i>git clone https://github.com/ScryptBrewer/AIQ_Workload_classification.git<br>
git clone https://github.com/NetApp/Ansible-with-Active-IQ-Unified-Manager.git</i></b>

Create the plugin module directory if it does not exist<br>
<b><em>mkdir -p  ~/.ansible/plugins/modules</em>

Copy the modules into the modules folder<br>
<b><i>cp Ansible-with-Active-IQ-Unified-Manager/aiqum_modules/* ~/.ansible/plugins/modules/</i>

Update the Acive IQ Server and credentials<br>
<b><em>vi aiqum_credentials.yml</em>

Update the volsource.csv file
Here is the header line for that file Performance and Efficiancies are defined in the AIQ ocum server 
Default Performance levels are <ul><li>Extreme Performance </li><li>Extreme for Database Data</li><li>Extreme for Database Shared Data</li><li>Extreme for Database Logs</li><li>Performance</li><li>Value</li><li>Unassigned]</li></ul>
Default efficianciey levels are <ul><li>High</li><li>Low</li></ul>
cluster,svm,volume,performance,(efficiency)

Execute the play<br>
<b><i>ansible-playbook aiqum_play.yml</i></b>


