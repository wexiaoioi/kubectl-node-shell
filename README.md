# kubectl node-shell

## Installation

```bash
curl -LO https://github.com/wexiaoioi/kubectl-node-shell/raw/master/kubectl-node_shell
chmod +x ./kubectl-node_shell
sudo mv ./kubectl-node_shell /usr/local/bin/kubectl-ns
```

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