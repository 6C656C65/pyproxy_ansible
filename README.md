<div align="center">
  <h1>pyproxy Ansible</h1>
</div>

**pyproxy Ansible** is an Ansible role for deploying the [pyproxy](https://github.com/6C656C65/pyproxy) project.

## ⚡ **Deployment Methods**

| Feature              | Supported |
| -------------------- | --------- |
| From source          | ✅        |
| Using Docker run     | ✅        |
| Using Docker Compose | ✅        |

## 📦 **Installation**

You can add the role to your playbook as a submodule. For example:

```bash
git submodule add https://github.com/6C656C65/pyproxy_ansible roles/pyproxy
```

## 🔧 **Configuration**

By default, the installation method uses Docker Compose.
You can change the installation method and adjust other settings in the `./defaults/main.yml` file, either directly or by overriding variables in your playbook.

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 **Contributing**

Contributions are always welcome and appreciated! If you'd like to improve this project, feel free to fork the repository and submit a pull request. Whether it's fixing bugs, adding new features, improving documentation, or suggesting enhancements, every contribution helps. Please ensure you follow the coding standards and test your changes before submitting. Let's build something great together!
