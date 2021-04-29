# k8s-util

## Quickstart
```
sudo apt install pkg-config
git clone https://github.com/ahmetb/kubectx.git ~/.kubectx
COMPDIR=$(pkg-config --variable=completionsdir bash-completion)
sudo ln -sf ~/.kubectx/completion/kubens.bash $COMPDIR/kubens
sudo ln -sf ~/.kubectx/completion/kubectx.bash $COMPDIR/kubectx
git clone https://github.com/jonmosco/kube-ps1.git
curl -LO https://github.com/kvaps/kubectl-node-shell/raw/master/kubectl-node_shell
chmod +x ./kubectl-node_shell
sudo mv ./kubectl-node_shell /usr/local/bin/kubectl-node_shell
cat <<EOF >> ~/.bashrc
#kubectx and kubens
export PATH=~/.kubectx:$PATH

source ~/kube-ps1/kube-ps1.sh
PS1='[\u@\h \W $(kube_ps1)]\$ '

alias k="kubectl"
alias kd="kubectl describe"
alias kg="kubectl get"
alias kl="kubectl logs -f"
EOF
```
