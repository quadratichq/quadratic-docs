---
description: Deploy Quadratic with Docker to almost any hardware.
---

# Docker

Docker deployments with Quadratic are a few easy steps away. Instructions vary depending on operating system.&#x20;

## MacOS and Linux

**Basic requirements:**&#x20;

* License Key (available at [https://selfhost.quadratichq.com/](https://selfhost.quadratichq.com/))
* The following open ports: 80, 443, 3001, 3002, 3003, 4433, 4455, and 8000
* [Docker](https://www.docker.com/get-started/)

```bash
curl -sSf https://raw.githubusercontent.com/quadratichq/quadratic-selfhost/main/init-local.sh -o init.sh && bash -i init.sh
```

This will start the process of downloading and running containers, also prompting for the license key that you can acquire for free at [https://selfhost.quadratichq.com/](https://selfhost.quadratichq.com/). Quadratic self-hosting is free for up to three users on a single deployment.&#x20;

Need help? Enterprise users can  [Contact us](https://quadratichq.com/contact).

## Windows

Running on Windows requires using WSL 2 with Docker integration enabled.&#x20;

1. WSL 2 set up, here are installation instructions: [https://learn.microsoft.com/en-us/windows/wsl/install](https://learn.microsoft.com/en-us/windows/wsl/install)
2. Add Docker to WSL: [https://docs.docker.com/desktop/features/wsl/](https://docs.docker.com/desktop/features/wsl/)
3. Retrieve license key: [https://selfhost.quadratichq.com/](https://selfhost.quadratichq.com/)
4. Run command to download and run containers, this step will also prompt for license&#x20;

```bash
curl -sSf https://raw.githubusercontent.com/quadratichq/quadratic-selfhost/main/init-local.sh -o init.sh && bash -i init.sh
```

Need help? Enterprise users can  [Contact us](https://quadratichq.com/contact).

## Common errors

**Toomanyrequests**: this error will happen if you have not logged in to Docker when trying to download and run containers. Use `Docker login` in your terminal to fix.&#x20;

**Error getting credentials:** [https://forums.docker.com/t/error-failed-to-solve-error-getting-credentials-err-exit-status-1-out/136124](https://forums.docker.com/t/error-failed-to-solve-error-getting-credentials-err-exit-status-1-out/136124)

**Docker + WSL virtualization errors:** ensure virtualization is enabled in your BIOS: [https://support.microsoft.com/en-us/windows/enable-virtualization-on-windows-c5578302-6e43-4b4b-a449-8ced115f58e1](https://support.microsoft.com/en-us/windows/enable-virtualization-on-windows-c5578302-6e43-4b4b-a449-8ced115f58e1)

## Contact us

Enterprise users can [contact us](https://quadratichq.com/contact) if you need any more help setting up a deployment of Quadratic using Docker.&#x20;
