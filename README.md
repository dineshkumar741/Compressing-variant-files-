# Compressing-variant-files-
VCF files compression &amp; decompression


How to decompress files and restoring them at your end:

# GSC (Genotype Sparse Compression): 

    1. Clone repository in terminal: git clone https://github.com/luo-xiaolong/GSC.git  
    2. cd gsc
    3. make
    4. nano ~/.bashrc
    5. Setting up path for global access: (specify the path where you have installed gsc)
        export PATH=$PATH:/media/ricky/EXTERNAL_USB/redamane_data/new_python_code/GSC/
    6. Ctrl+O
    7. Enter
    8. Ctrl+X
    9. source ~/.bashrc
    
The above steps are required to set up GSC on your machine. So when you use GSC for the first time you just follow these steps.

Now go to the directory where you have downloaded the files and open terminal:


** 1> tar -xvzf all_samples.tar.gz (decompress .tar.gz)**


** 2> now you have 10 .gsc files and time to restore them back to .vcf files.**


** for i in $(sample 1 10); do

gsc decompress --in XY_${i}_annotated.gsc --out XY_${i}_annotated.vcf

done **


Now you have files decompressed from 30mb to 700mb


# How to compress VCF files to .tar.gz:	


  ** 1. for i in $(sample 1 10); do
  
      gsc compress --in XY_${i}_annotated.vcf --out XY_${i}_annotated.gsc
      
      done **
      
  ** 2. tar -cvzf all_samples.tar.gz *_annotated.gsc** 
  

Now you have file compressed from 700mb to 30mb
