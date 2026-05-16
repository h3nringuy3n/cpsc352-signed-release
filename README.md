# cpsc352-signed-release
Group members and contributions: 

Henri Nguyen - GitHub repo setup & actions workflow & backend build

Huy Bui - GPG Key Management & crypto logic

Kedar Patil - Testing & documentation

Eric Solorzano - Testing & documentation

Philip Ma - Testing & documentation

Kelsey Tang - Presentation



#How to verify release

- ensure the following is configured on local device:
	1. Git
	2. Gpg (GnuPGG)

- clone the repo

- navigate to releases to get checksums

	 navigate to https://github.com/h3nringuy3n/cpsc352-signed-release/releases/
	
	download the assets in the same repo: 
		1) hello.exe
		2) SHA256SUMS
		3) SHA256SUMS.acs

- import the public key to gpg

	gpg --import public_key.asc

- verify the signature

	gpg --verify SHA256SUMs.asc SHA256SUMS

- verify the checksum
	
	sha256sum --check SHA256SUMS	 --ignore-missing
