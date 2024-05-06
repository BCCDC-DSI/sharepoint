# Topics



<details>

   <summary>Python Infrastructure</summary>
   

*This page will be documenting ideas and examples related to storage, systems and network management in Python workflows. Please visit the 
[Python Overview]( https://healthbc.sharepoint.com/sites/BCCDCDataAnalyticsServicePHSA/SitePages/python-main.aspx) for an introduction on working in Python at BCCDC.*

# Reproducible workflows

Python users are encouraged to create a new ***virtual environment*** for each new Python project. Please review [instructions](https://healthbc.sharepoint.com/sites/BCCDCDataAnalyticsServicePHSA/SitePages/virtual-environments.aspx) that have been tested on PAWS on April 10, 2024.

# Integrated development environments

- [Codespace](https://github.com/codespaces) (online via GitHub/ GitLab)
- PyCharm
- Visual Studio Code

# Path specifications in Linux and Windows

- To change into a **shared network directory** using the ```Path``` package (```O``` drive):
```
from pathlib import Path
os.chdir(Path('//srvnetapp02.phsabc.ehcnet.ca/bccdc/Depts/Analytics/'))
```


- To change into the **personal directory** (```U``` drive):
```
os.chdir(Path('//PHSAhome2.phsabc.ehcnet.ca/jane.doe/'))
```


- Using functions in package ```os```:
```
os.path.join('C:\\Users\\jane.doe', filename)
```

Please review [other examples](https://www.pythoncheatsheet.org/cheatsheet/file-directory-path).


</details>


