# UKBB-Data

## 1. Dataset Overview
   The UK Biobank is a large-scale, population-based cohort study involving over 500,000 UK residents aged 40–69 years. Recruitment took place between 2006 and 2010, during which participants completed extensive health questionnaires, underwent detailed physical assessments, and provided biological samples. The study tracked health-related events through data linkage to hospital admission records and mortality registries. In 2009, the UK Biobank introduced ophthalmic examinations to further expand the scope of the collected data[[1]](https://bjo.bmj.com/content/bjophthalmol/107/4/547.full.pdf).  
   
   Homepage of the dataset： https://www.ukbiobank.ac.uk/

## 2. Our current dataset (continuously updated)
  The data we currently possess mainly includes: Retinal images, and health-realted data.
   
  Dataset path:  */scratch/users/nus/hongyu.h*

   ### 1. Retianl images
   
   Dataset path: */scratch/users/nus/hongyu.h/SERI_UKbiobank/1_Fundus_Images*

   #### a. #NUMBER
      UKBB_FP_01 : 46514  
      UKBB_FP_02 : 40826  
      UKBB_FP_03 : 38786  
      UKBB_FP_04 : 49705  
      UKB_new_2024: 1169 + 949 + 1154 + 1 +923 = 4196  
      Total count of retinal images：180027  

   #### b. INSTANCE
   Interpretation of the naming format： *Participants ID_Data field_Instances_Array*  
   Detailed information is available on the [official website](https://biobank.ndph.ox.ac.uk/showcase/field.cgi?id=21015).
   
  <table>
  <tr>
    <td>
      <img src="https://github.com/xuting42/UKBB-Data/blob/main/imgs/1017168_21016_2_1.png" width="300px">
      <br>1017168_21016_2_1.png
    </td>
    <td>
      <img src="https://github.com/xuting42/UKBB-Data/blob/main/imgs/1021021_21015_2_1.png" width="300px">
      <br>1021021_21015_2_1.png
    </td>
  </tr>
</table>

### 2.Health-related data
Dataset path: */scratch/users/nus/hongyu.h/SERI_UKbiobank/2_Phenptype*

The raw data we possess is stored in the *"/0_Header_Tab"* folder, and the other folders contain the organized data required for 
other projects.

In the *"/0_Header_Tab"* folder, we have *header.txt* file and its corresponding *xxx.tab* file. The tab file serves as the main data file, while the header file is created by extracting the header from the main data file. Therefore, if you want to understand the data needed for your project, you can search for the corresponding field ID on the UKB website and then check if the header files contain the corresponding data.

   #### Example of extracting ethnic data
  If we want to extract ethnic data, we need to go to the [UKBB website](https://biobank.ndph.ox.ac.uk/showcase/search.cgi) and find the field ID for ethnic data. 
 
  <img src="https://github.com/xuting42/UKBB-Data/blob/main/imgs/biobank_search.png" width="500px">
  
  It can be found that the field ID for ethnic data is 21000, and detailed information about the [ethnic data](https://biobank.ndph.ox.ac.uk/showcase/field.cgi?id=21000) can also be obtained.
  
  First, let's find the location of the ethnic data within the header file.

  `grep -n '21000' *.txt` 

  We can obtain the search result

```
D3_ukb41252_tab_8330_header.txt:4737:  4737  f.20160.0.0
D3_ukb41252_tab_8330_header.txt:4738:  4738	f.20160.1.0  
D3_ukb41252_tab_8330_header.txt:4739:  4739	f.20160.2.0  
D3_ukb41252_tab_8330_header.txt:4740:  4740	f.20160.3.0
```
According to the ethnic data detailed information, we select 'f.20160.0.0.', which is located at row 4737 in *D3_ukb41252_tab_8330_header.txt*.

Then, we can extract the ethnic data from the corresponding tab file.

`cut -f 1,4737  /scratch/users/nus/hongyu.h/SERI_UKBiobank/2_Phenotype/ukb41252.tab >  xxx/ethnic.txt`

Through the simple steps mentioned above, we can locate and extract the necessary data for the project.

## 3.Our project data

Hey everyone.

I've gone ahead and created a *"3_Project"* folder to help keep our project data organized. Feel free to create your own subfolders within it to store any data you've prepared for your specific needs.

To make things easier, I've also set up a *"basic"* folder that has essential data like gender and ethnic, since most of our projects rely on this info. Having it all in one place should save us some time and effort.

Let me know if you have any thoughts or suggestions!

  
  
      





#### Reference

[[1]](https://bjo.bmj.com/content/bjophthalmol/107/4/547.full.pdf) Zhu, Zhuoting, et al. "Retinal age gap as a predictive biomarker for mortality risk." British Journal of Ophthalmology 107.4 (2023): 547-554.
