# AnsibleTowerVaultTest
Testing an Ansible Vault issue

Vault Password: TestMe

Running from command line (Ansible 2.0.1) :
> ansible-playbook -i testhosts tester.yml -e "hosts=Dev1.Linux" --ask-vault-pass --private-key=~/.ssh/id_rsa

Running from Tower :
1. Add project
2. Add inventory named Dev.All
3. Add child group Dev1.All in Dev.All
4. Add child groups Dev1.Linux and Dev1.Windows in Dev1.All
5. Add host localhost to Dev1.Linux
6. Add host windows-host to Dev1.Windows
7. Add credential with private key (that can ssh to localhost)
8. Add job configuration referencing "tester.yml" in project, passing in extra variable "hosts" set to "Dev1.Linux"
