# UKBB-Data

## 1. Dataset Overview
   The UK Biobank is a large-scale, population-based cohort study involving over 500,000 UK residents aged 40–69 years. Recruitment took place between 2006 and 2010, during which participants completed extensive health questionnaires, underwent detailed physical assessments, and provided biological samples. The study tracked health-related events through data linkage to hospital admission records and mortality registries. In 2009, the UK Biobank introduced ophthalmic examinations to further expand the scope of the collected data[[1]](https://bjo.bmj.com/content/bjophthalmol/107/4/547.full.pdf).  
   
   Homepage of the dataset： https://www.ukbiobank.ac.uk/

## 2. Our current dataset (continuously updated)
  The data we currently possess mainly includes: Retinal images, and health-realted information.
   
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
   Detailed information is available on the official website.
   
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

### 2.Health-related information
Dataset path: */scratch/users/nus/hongyu.h/SERI_UKbiobank/2_Phenptype*

The raw data we possess is stored in the *"/0_Header_Tab"* folder, and the other folders contain the organized data required for 
Pro. Cheng's other projects.

In the *"/0_Header_Tab"* folder, we have *header.txt* file and its corresponding *xxx.tab* file. The tab file serves as the main data file, while the txt file is created by extracting the header from the main data file. Therefore, if you want to understand the data needed for your project, you can search for the corresponding field ID on the UKB website and then check if the header contains the corresponding data.

   #### Example of extracting ethnic data
  If we want to extract ethnic data, we need to go to the [UKBB website](https://biobank.ndph.ox.ac.uk/showcase/search.cgi) and find the field ID for ethnic data. 
  
      





#### Reference

[[1]](https://bjo.bmj.com/content/bjophthalmol/107/4/547.full.pdf) Zhu, Zhuoting, et al. "Retinal age gap as a predictive biomarker for mortality risk." British Journal of Ophthalmology 107.4 (2023): 547-554.
