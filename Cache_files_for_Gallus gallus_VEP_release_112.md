# Installation process of 'Cache files'  of VEP release-112 for ***'Gallus gallus'***





## Step-1: **Create a Directory** under vep

It's recommended to create a specific directory to store the cache files. For example, using the following command, we are creating a new directory- 'cache' and then navigating to that directory:

```sh
mkdir -p ~/vep_112/cache
cd ~/vep_112/cache
```



## Step-2: Download 'cache' files from Ensembl FTP server

You can download the cache files directly from the Ensembl FTP site. For VEP release 112 ***Gallus gallus***, use the following `wget` command:  

```sh
wget ftp.ensembl.org/pub/release-112/variation/vep/gallus_gallus_vep_112_bGalGal1.mat.broiler.GRCg7b.tar.gz
```



## Step-3: Extract the 'Cache' Files 

After downloading, extract the tarball in the cache directory:

```sh
tar -xzf gallus_gallus_vep_112_bGalGal1.mat.broiler.GRCg7b.tar.gz
```



## Step-4: Configure VEP 

When running VEP, use the ***--dir_cache*** option to point to the cache directory:

```sh
vep \
 -i ${input_file} \
 -o ${out_dir}/output_file_name.txt \
 --cache \
 --dir_cache ~/vep_112/cache \
 -species gallus_gallus \
 --symbol \
 --sift b \
 --offline \
 --variant_class \
 --protein \
 --uniprot \
 --pubmed \ 
 --stats_file${out_dir}/output_html_file_name

# add other flags whatever you need 
```

This will ensure VEP uses the locally stored cache files for ***Gallus gallus*** from release 112.



## Step-5: Optional- Remove the 'tar' file

You may want to remove the tarball after extraction to save space:

```sh
rm gallus_gallus_vep_112_bGalGal1.mat.broiler.GRCg7b.tar.gz
```

Now you're all set to run VEP with the Gallus gallus cache for release 112!