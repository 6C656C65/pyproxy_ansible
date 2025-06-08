<div align="center">
  <h1>pyproxy Ansible</h1>
</div>

**pyproxy Ansible** is an Ansible role for deploying the [pyproxy](https://github.com/pyproxytools/pyproxy) project.

## ⚡ **Deployment Methods**

| Feature              | Supported |
| -------------------- | --------- |
| From source          | ✅        |
| Using package        | ✅        |
| Using Docker run     | ✅        |
| Using Docker Compose | ✅        |

## 📦 **Installation**

You can add the role to your playbook as a submodule. For example:

```bash
git submodule add https://github.com/pyproxytools/pyproxy-ansible roles/pyproxy
```

## 🔧 **Configuration**

By default, the installation method uses Docker Compose.
You can change the installation method and adjust other settings in the `./defaults/main.yml` file, either directly or by overriding variables in your playbook.

### 🔐 **SSL Certificate Handling**

If you want to provide your own SSL inspection certificates, you can configure the role to copy them to the target machine.

* Set the variable `pyproxy."method".ssl_inspect_ca_folder` to the **path of the folder** containing your certificates (e.g. `certs/`).
* The expected files inside this folder are typically `cert.pem` and `key.pem` or a custom CA used by pyproxy.
* These files will be copied to `{{ pyproxy."method".install_path }}/certs/ca`.

For example for the docker method here are some variables :
```yaml
pyproxy:
  docker:
    ssl_inspect_ca_folder: "certs/"
    volumes:
      - source: /opt/pyproxy/certs/ca
        target: /app/certs/ca
        type: folder
```
Don't forget to add the CA volume for the "compose" and "docker" methods.

⚠️ If the variable `pyproxy.docker.ssl_inspect_ca_folder` is **not defined**, the certificate copy step is skipped automatically.

> The path is resolved relative to the role or playbook. Make sure the folder exists and is accessible during the playbook run.

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 **Contributing**

Contributions are always welcome and appreciated! If you'd like to improve this project, feel free to fork the repository and submit a pull request. Whether it's fixing bugs, adding new features, improving documentation, or suggesting enhancements, every contribution helps. Please ensure you follow the coding standards and test your changes before submitting. Let's build something great together!
