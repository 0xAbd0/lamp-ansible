Automate LAMP Stack Deployment (Using Ansible)

Objective:
Create an Ansible playbook to deploy and configure a LAMP stack (Linux, Apache, MySQL, PHP) on multiple servers.

Requirements:
	1.	Best Practices:
		•	Use roles to structure your playbook cleanly.
		•	Use blocks for logically grouped tasks.
		•	Use includes/imports where necessary to keep the playbooks modular.
		•	Implement error handling with rescue and always blocks.
		•	Add notification tasks using handlers (e.g., restart Apache after config change).
	2.	Functional Requirements:
		•	Install and configure Apache with a sample index.php.
		•	Install and secure MySQL (include root password setup and secure installation).
		•	Install PHP and confirm Apache can process PHP files.
	3.	Extras (Bonus Points):
		•	Add firewall rules (e.g., UFW) to allow web traffic (port 80/443).
		•	Create a separate inventory file and support different environments (e.g., dev, prod).
