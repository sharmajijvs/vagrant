Setup
=====
1. Download and install virtualbox (https://www.virtualbox.org/)
2. Download and install vagrant (http://vagrantup.com)

Summary
=======
This test simulates real world problems a Dev/Ops Engineer may face and have to solve. You will have to learn how to use (potentially) new tools, diagnose system health issues, write some utilities, and automate the whole process to end up with a reproducable image.

At the end of this you should be able to send a new Vagrantfile and associated scripts/configs that will allow the interviewer to recreate your completed and fixed test environment from the same base image provided in the test Vagrantfile.

Instructions
============
1. Learn the basics of how to use Vagrant, launch the vagrant VM, and login to it via SSH (Note: this will take some time to download the VM image the first time) ....done
2. Analyze the health of the system. Note anything you find and fix if there are issues.
3. Ensure nginx is running. If is is not, diagnose and fix. 
	- You should be able to see a test page going here in your browser: http://localhost:8080
4. Reconfigure nginx to run using HTTPS rather than HTTP. Any HTTP links should redirect to HTTPS.
	- You should be able to see the exact same test page as above by going here in your browser: https://localhost:8443
	- You will get an exception about an insecure connection due to the self-signed cert. Feel free to ignore this.
5. Add a cronjob that runs /opt/cronjob.sh once per minute
6. Write your own vagrant file and provisioning scripts/configs that recreate everything you just did. 
7. Create a tar.gz of your new vagrant file with any associated provisioning scripts/configs and send back to the interviewer.

The interviewer should be able to simply un-tar your archive, run `vagrant up`, and have your completed and fixed environment running for review.