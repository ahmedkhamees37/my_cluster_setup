# My Cluster Setup! 🚀 Your High-Availability Journey Starts Here!

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## Hey there! 👋 What's this all about?

This project is your go-to solution for effortlessly setting up a super reliable, high-availability cluster. We're talking **Pacemaker**, **Corosync**, and **PCS** – all working together to keep your systems running smoothly! And the best part? It's all automated with **Ansible** playbooks, meaning less headache for you, fewer errors, and consistent setups across all your Linux nodes. Think of it as your personal cluster-building assistant! 🤖

---

## Check out the magic! 🌟

You can find all the code right here: [https://github.com/ahmedkhamees37/my_cluster_setup](https://github.com/ahmedkhamees37/my_cluster_setup)

---

## What can this do for you? ✨

This awesome setup handles a bunch of things to get your cluster humming:

* **Installs all the goodies**: Gets `pacemaker`, `corosync`, and `pcs` installed on every node.
* **Network wizardry**: Sets up your network interfaces perfectly for that crucial cluster heartbeat.
* **Friendly names**: Manages hostnames and `/etc/hosts` so your nodes can chat easily.
* **Time sync**: Keeps all your nodes on the same clock – no more time discrepancies!
* **Service kickoff**: Starts and enables essential cluster services like `pcsd`.
* **Password power-up**: Securely sets the `hacluster` user password with Ansible.
* **Cluster handshake**: Authenticates and sets up all your cluster nodes.
* **Smart and sturdy**: Built with Ansible's best practices for error handling and idempotency – meaning it's smart enough to know what's already done and won't break things if you run it multiple times.

---

## Before you dive in... 🛠️

Just a few things you'll need to have ready:

* **A few Linux pals**: Grab some CentOS/RHEL (or compatible) Linux nodes.
* **SSH access**: Make sure you can SSH into all your nodes with proper privileges (passwordless sudo is highly recommended for smooth sailing!).
* **Ansible on your control machine**: This is where you'll be running the playbook from.
* **Node name resolution**: Ensure your nodes can find each other, either through DNS or by popping entries into `/etc/hosts`.
* **Firewall friendly**: Your firewalls need to allow traffic on required ports, especially **TCP 2224** for `pcsd`!

---

## Ready to roll? Let's go! 🚀

Getting your cluster up and running is super easy:

1.  **Clone the repo**:
    ```bash
    git clone [https://github.com/ahmedkhamees37/my_cluster_setup.git](https://github.com/ahmedkhamees37/my_cluster_setup.git)
    cd my_cluster_setup
    ```

2.  **Tell Ansible about your nodes**: Create an `inventory.ini` file and list your cluster nodes there.

3.  **Customize (and secure!)**: Tweak variables like your `pcs_password` in your inventory, or even better, use **Ansible Vault** for top-notch security!

4.  **Unleash the playbook!**:
    ```bash
    ansible-playbook -i inventory.ini playbook.yml
    ```

5.  **Watch the magic happen**: Keep an eye on the output to see your cluster come to life!

### A little heads-up! ⚠️

* Always double-check that your network and firewalls allow communication on **port 2224** between your nodes. It's crucial!
* This playbook uses Ansible’s `become` feature, so make sure your user has `sudo` privileges.
* If your system uses different network interface names, you might need to adjust those in the variables.
* Don't worry about the `hacluster` password; the playbook sets it securely using hashed values!

---

## Want to contribute? We'd love that! 💖

Have ideas? Found a bug? Want to add a cool feature? We're all ears! Feel free to [open an issue](https://github.com/ahmedkhamees37/my_cluster_setup/issues) or [submit a pull request](https://github.com/ahmedkhamees37/my_cluster_setup/pulls). Your contributions make this project even better!

---

## License 📜

This project is rocking the MIT License – check out the [LICENSE](LICENSE) file for all the details.

---

## Let's connect! 📧

Have questions or just want to say hi?

**Ahmed Khamees**
* **GitHub**: [@ahmedkhamees37](https://github.com/ahmedkhamees37)
* **Email**: your-email@example.com

---

Ready to build your robust, high-availability cluster with ease? Let me know if you have any questions!
