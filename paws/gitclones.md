# Cloning repositories in PAWS 

[Page under construction]

1. On your lab station but outside of PAWS, install ***Anaconda3***

    a. Login to [Central Analytics Platform](https://apps.phsa.ca/logon/LogonPoint/tmindex.html). Under ***APPS***, click on ***Anaconda3***. This will download a connection file that effectively installs ***Anaconda3*** on your station. 

    b. Alternatively, if you have administrative rights on your station, you may download and install a mini version of this software called [Miniconda3](https://docs.anaconda.com/miniconda/). You may opt out of email subscription.
2. Login to PAWS and complete the following steps in PAWS. 
3. Click on the START menu and click on ***Anaconda Power Prompt***
4. Using the ***Power Prompt***, navigate to the location where you would like to place the "clone".

    For instance, type in the prompt to navigate to the ```W``` drive (note the colon):

    ```
    w:
    ```

    Press ENTER and type "cd" (which stands for "change directory")

    ```
    cd nb0

    ```

    Press TAB key to see suggestions from ***Power Prompt*** (which is the so-called "auto-completion" feature). Repeat as needed until you reach to the destination folder. 


5. Once you have navigated to the subdirectory where you would clone, issue the following:

    ```git clone https://github.com/someone/some_repo.git```


Note that the settings in PAWS do not permit ```git push``` (writing back to the remote site).


<br><br>
Below is an example for cloning from a real URL of an existing repo.

```git clone https://github.com/BCCDC-DSI/Python-Git-workshop.git```



<br>
![image](figures/finding_repo_url.png)
