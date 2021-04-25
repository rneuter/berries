
<!-- PROJECT SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- GOAL -->
## k3s berries

This is all about building a simple Raspberries Kubernetes cluster with k3s and Ansible. This project does not handle HA for the Kubernetes cluster and it is supposed to work with :
- 1 master node
- n worker node(s)

### Built With

* [Ansible](https://docs.ansible.com)

<!-- GETTING STARTED -->
## Getting Started

### Prerequisites

- Berries should run a Debian like Linux distribution
- Berries should use an ethernet connection
- SSH access to your berries via SSH keys
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/index.html) on your local machine

### Installation

1. Clone the repo

   ```sh
   git clone git@github.com:rneuter/berries.git
   ```

2. Update `berries.yml` inventaire with your current setup (it is recommended to use a fix IP address for each berry to not have to update this file several times)

3. Test your setup

   ```sh
   ansible all -i berries.yml -m ping

    node02 | SUCCESS => {
        "changed": false, 
        "ping": "pong"
    }
    master01 | SUCCESS => {
        "changed": false, 
        "ping": "pong"
    }
    node01 | SUCCESS => {
        "changed": false, 
        "ping": "pong"
    }

   ```

<!-- USAGE EXAMPLES -->
## Usage

```sh
# Check what tasks will run on berries
ansible-playbook cluster.yml -i berries.yml --list-tasks
```

```sh
# Run all tasks
ansible-playbook cluster.yml -i berries.yml
```

```sh
# Run all tasks with the tag setup
ansible-playbook cluster.yml -i berries.yml --tags setup
```

## Next step

- [Monitoring your cluster](https://github.com/rneuter/monitoring-helm-charts)


<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [Best README Template](https://github.com/othneildrew/Best-README-Template)


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/rneuter/berries.svg?style=for-the-badge
[contributors-url]: https://github.com/rneuter/berries/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/rneuter/berries.svg?style=for-the-badge
[forks-url]: https://github.com/rneuter/berries/network/members
[stars-shield]: https://img.shields.io/github/stars/rneuter/berries.svg?style=for-the-badge
[stars-url]: https://github.com/rneuter/berries/stargazers
[issues-shield]: https://img.shields.io/github/issues/rneuter/berries.svg?style=for-the-badge
[issues-url]: https://github.com/rneuter/berries/issues
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/rneuter
