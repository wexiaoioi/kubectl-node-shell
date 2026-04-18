# kubectl node-shell

## Installation

```bash
curl -LO https://github.com/wexiaoioi/kubectl-node-shell/raw/master/kubectl-node_shell
chmod +x ./kubectl-node_shell
sudo mv ./kubectl-node_shell /usr/local/bin/kubectl-ns
```
<img width="1075" height="282" alt="image" src="https://github.com/user-attachments/assets/54f0ee42-5b57-40d1-ba3b-6b4d39697d6e" />


## Usage

```bash
# Get standard bash shell
kubectl ns <node>

# Use custom image for pod
kubectl ns <node> --image <image>

# Use X-mode (mount /host, and do not enter host namespace)
kubectl ns -x <node>

# Skip specific namespace types to enter, choose any of ipc, mount, pid, net, uts
kubectl ns <node> --no-ipc

# Execute custom command
kubectl ns <node> -- echo 123

# Use stdin
cat /etc/passwd | kubectl ns <node> -- sh -c 'cat > /tmp/passwd'

# Run oneliner script
kubectl ns <node> -- sh -c 'cat /tmp/passwd; rm -f /tmp/passwd'
```
<img width="1462" height="270" alt="image" src="https://github.com/user-attachments/assets/63375c0e-5730-4daf-8e3b-e7d29380e3e3" />
