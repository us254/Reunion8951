
Command for Ubuntu server to remove non-printable characters from a file using awk and overwrite the file with the cleaned version:

```
awk '{ gsub(/[\000-\037]/,"") } 1' /root/generate-cert.sh > /root/generate-cert_cleaned.sh && mv /root/generate-cert_cleaned.sh /root/generate-cert.sh
```

This command uses awk to clean up the file `/root/generate-cert.sh` and remove unwanted characters that are non-printable. The cleaned file is then overwritten to `/root/generate-cert.sh` after first saving a copy of the cleaned file to `/root/generate-cert_cleaned.sh`.

To use this command for a different file, replace `/root/generate-cert.sh` with the path to the file you want to clean.

Additionally, the following command removes non-printable characters from `/root/tls_h2_check.sh` file using the same awk command, saves the cleaned file to `/root/tls_h2_check_cleaned.sh`, and then overwrites the original file with the cleaned version:

```
awk '{ gsub(/[\000-\037]/,"") } 1' /root/tls_h2_check.sh > /root/tls_h2_check_cleaned.sh && mv /root/tls_h2_check_cleaned.sh /root/tls_h2_check.sh
```

Lastly, to make `/root/tls_h2_check.sh` executable, the following two commands are used:

```
sudo chmod +x /root/tls_h2_check.sh
sudo /root/tls_h2_check.sh
```

The first command grants executable permissions to `/root/tls_h2_check.sh` and the second command runs the script.
