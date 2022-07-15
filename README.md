# cloudflare-ssh-browser-terraform-digitalocean

# 🚀 Browser-based SSH using Cloudflare & Terraform on Digitalocean 🚀

https://github.com/coding-to-music/cloudflare-ssh-browser-terraform-digitalocean

From / By Paolo Tagliaferri https://github.com/Vortexmind

https://github.com/Vortexmind/cloudflare-ssh-browser

https://www.paolotagliaferri.com/secure-in-browser-ssh-with-cloudflare-terraform-digitalocean/

https://docs.digitalocean.com/reference/terraform/reference/resources/droplet/

## Environment variables:

```java

```

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/cloudflare-ssh-browser-terraform-digitalocean.git
git push -u origin main
```

# 👷 Browser-based SSH using Cloudflare & Terraform

Tutorial code demonstrating how to implement Zero Trust, browser based SSH authentication to access a Digitalocean VM.
Most of the set up is fully automated using Terraform.

## Documentation

This tutorial is [fully explained in the article published on my blog](https://www.paolotagliaferri.com/secure-in-browser-ssh-with-cloudflare-terraform-digitalocean/)

## License

This work is available under [MIT License](https://github.com/Vortexmind/cloudflare-ssh-browser/blob/main/LICENSE)

## terraform init

```
tf init
```

Output:

```
Initializing the backend...

Initializing provider plugins...
- Reusing previous version of cloudflare/cloudflare from the dependency lock file
- Reusing previous version of digitalocean/digitalocean from the dependency lock file
- Reusing previous version of hashicorp/http from the dependency lock file
- Installing cloudflare/cloudflare v3.1.0...
- Installed cloudflare/cloudflare v3.1.0 (signed by a HashiCorp partner, key ID DE413CEC881C3283)
- Installing digitalocean/digitalocean v2.12.0...
- Installed digitalocean/digitalocean v2.12.0 (signed by a HashiCorp partner, key ID F82037E524B9C0E8)
- Installing hashicorp/http v2.1.0...
- Installed hashicorp/http v2.1.0 (signed by HashiCorp)

Partner and community providers are signed by their developers.
If you'd like to know more about provider signing, you can read about it here:
https://www.terraform.io/docs/cli/plugins/signing.html

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

## terraform plan

```
tf plan
```

Output

```
data.http.my_ip: Reading...
data.cloudflare_ip_ranges.cloudflare: Reading...
data.cloudflare_zones.configured_zone: Reading...
data.digitalocean_ssh_key.default: Reading...
data.http.my_ip: Read complete after 0s [id=https://ipv4.icanhazip.com]
data.digitalocean_ssh_key.default: Read complete after 1s [name=Sept-23-2021]
data.cloudflare_ip_ranges.cloudflare: Read complete after 1s [id=2749251940]
data.cloudflare_zones.configured_zone: Read complete after 1s [id=010561c6841c1d1ab17e671680567a3f]

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create
 <= read (data resources)

Terraform will perform the following actions:

  # data.digitalocean_droplet.ssh_droplet will be read during apply
  # (depends on a resource or a module with changes pending)
 <= data "digitalocean_droplet" "ssh_droplet" {
      + backups              = (known after apply)
      + created_at           = (known after apply)
      + disk                 = (known after apply)
      + id                   = (known after apply)
      + image                = (known after apply)
      + ipv4_address         = (known after apply)
      + ipv4_address_private = (known after apply)
      + ipv6                 = (known after apply)
      + ipv6_address         = (known after apply)
      + ipv6_address_private = (known after apply)
      + locked               = (known after apply)
      + memory               = (known after apply)
      + monitoring           = (known after apply)
      + name                 = "cloudflare-ssh-broswer-droplet"
      + price_hourly         = (known after apply)
      + price_monthly        = (known after apply)
      + private_networking   = (known after apply)
      + region               = (known after apply)
      + size                 = (known after apply)
      + status               = (known after apply)
      + tags                 = (known after apply)
      + urn                  = (known after apply)
      + vcpus                = (known after apply)
      + volume_ids           = (known after apply)
      + vpc_uuid             = (known after apply)
    }
```

## terraform apply -auto-approve

tf apply -auto-approve

```

```

## terraform destroy -auto-approve

tf destroy -auto-approve

```
cloudflare_access_policy.ssh_policy: Destroying... [id=9e7356f8-469c-4876-a65f-9eac4b5ab2e2]
cloudflare_record.ssh_app: Destroying... [id=9da15f2c7dc1714388cfd545b1d9ebb2]
digitalocean_firewall.cloudflare_browser_ssh: Destroying... [id=9e8b0012-c4da-45dc-98c3-01e1441c8a58]
digitalocean_project.cloudflare_ssh_browser: Destroying... [id=61186c17-af4e-430b-9a00-a766697fdc98]
digitalocean_firewall.cloudflare_browser_ssh: Destruction complete after 0s
cloudflare_record.ssh_app: Destruction complete after 1s
cloudflare_access_policy.ssh_policy: Destruction complete after 2s
cloudflare_access_identity_provider.github_oauth: Destroying... [id=f260db82-502c-40b8-8354-5d87b899e399]
cloudflare_access_identity_provider.github_oauth: Destruction complete after 0s
digitalocean_project.cloudflare_ssh_browser: Destruction complete after 2s
digitalocean_droplet.ssh_droplet: Destroying... [id=308529051]
digitalocean_droplet.ssh_droplet: Still destroying... [id=308529051, 10s elapsed]
digitalocean_droplet.ssh_droplet: Still destroying... [id=308529051, 20s elapsed]
digitalocean_droplet.ssh_droplet: Destruction complete after 22s
cloudflare_access_ca_certificate.ssh_short_lived: Destroying... [id=514cfbc0f68d6e476fcbf2eb39610cd4282072f1e957f0fb]
cloudflare_argo_tunnel.ssh_browser: Destroying... [id=96dc3e1a-b9fe-4fb2-81da-d020348eb2ae]
cloudflare_access_ca_certificate.ssh_short_lived: Destruction complete after 0s
cloudflare_access_application.ssh_browser: Destroying... [id=2c67d15b-a699-4e4c-a505-feae77ebe4dc]
cloudflare_access_application.ssh_browser: Destruction complete after 1s
cloudflare_argo_tunnel.ssh_browser: Destruction complete after 1s

Destroy complete! Resources: 9 destroyed.
```
