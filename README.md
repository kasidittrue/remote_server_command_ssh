# Command working with remote server from Linux

## ssh from linux local machine  
**what for : connect to remote server : user@remotehost**     

ssh root@172.20.46.157  

## init command  
**what for : connect to network, conda not require ssl, cd to project directory**   

export http_proxy=http://proxy:80   
export https_proxy=http://proxy:80  
conda config --set ssl_verify no   
cd /data/prepaid/project  

## start up jupyter lab  
**what for : connect to remote server jupyter lab**    

### in remote xterm 
cd /data/prepaid  
jupyter lab --config jupyter_notebook_config.py --allow-root --no-browser  
http://172.20.46.157:8888/  

#### or start nohup(background)
cd /data/prepaid  
nohup jupyter lab --config jupyter_notebook_config.py --allow-root --no-browser &  
**when you want to end**  
jupyter notebook list  
netstat -tulpn|grep 8888  
kill PID  


## obsolete
### in remote server (alrady ssh)  
conda activate my_env  
jupyter notebook --no-browser --ip 172.20.46.157 --port ***YYYY*** --allow-root  
jupyter lab --no-browser --port=***YYYY*** --allow-root  

### in local mahine linux   
ssh -N -f -L localhost:***XXXX***:localhost:***YYYY*** root@172.20.46.157  

then localhost:***XXXX*** on web browser


