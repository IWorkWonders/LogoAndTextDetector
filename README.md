# Logo And Text Detector [LTD]

# IWorkWondersLabs - Intelligence Innovated.


###### A complete solution CLI tool to detect for patterns (logos/templates) or Textual Keywords in any Image format files or PDF documents in any given folder/directory structure and report the findings. 

###### A very useful tool for re-branding corporate projects to check for the reminiscence of logos or textual mentions in various documentations, ad campaign, rebranding documents, auto generated policy documents etc.

###### Useful to search for any pattern, shapes, alphabets, text, keywords in image or PDF document formats.

# LTD

![](https://github.com/IWorkWonders/LogoAndTextDetector/blob/master/LTD_LOGO.png?raw=true)

# Features:

### Search for sub image/logo/pattern in Images/PDF documents:
- Includes search of logo/pattern, in any image with multiple formats, and PDF documents in any directory structure.
- Detects logo/pattern in watermarks, which is difficult to identify programmatically,
- Detects logo/pattern in PDF embedded images as well.

### Search for textual keywords in Images/PDF documents:
- Includes search of text in any sized fonts 
- Includes search of text within the header, footer of PDF documents,
- Detects textual keywords in watermarks as well,
- Detects text in PDF embedded images.

### Can handle Image/PDF files with:
- low resolution, 
- different color schemes, 
- small or big in size, 
- different orientation (example: tilted).

### Excel based reports with clickable links and search results:
- Clickable links within the report to display search result images.
- The searched pattern/logo/text is highlighted on the search result image.
- Page number of the PDF file where the pattern was found is listed.
- PDF/Image file name and location is listed.
- Number of occurances of the textual keywords detected is listed.
- Text word and the line found at is highlighted.

### Log file for tracking progress and issues:
- Log file to track errors, issues and user actions.
- Each output of the program is captured in the log file.
- Helps in tracking down issues while executing the program.

### Image text extract:
- If any text was extracted from any image/pdf file page, the extract is dumped for further reference at a particular location, and is listed in log file. 
- This helps in understanding why a particular text keyword was not identified and change the passed keywords accordingly. 

### Backup of search results in image format:
- For each PDF file, a conversion folder is created where the resulting search images are placed for reference.
- For the text detection, if text is detected on a file, the file is stored as evidence and linked in the excel report and log file.


### Example:
- Let us consider that we need to find all occurances of "Axis Bank" and "HDFC Bank" logos and text in their respective brochures.
- We need to provide respective logo files (jpg,png,bmp,tiff,gif,) to the script as below:

#### AXIS BANK Logo file as below:
---
![axislogofull](https://user-images.githubusercontent.com/41651749/51181392-10d39f00-18f1-11e9-95ef-8f2b0e80dee2.png)
---

#### HDFC BANK Logo file as below:
---
![hdfclogofull](https://user-images.githubusercontent.com/41651749/51181393-10d39f00-18f1-11e9-8905-a85c485fbeda.png)

- Now, we need to find occurances of the above logo files in the respective PDF brochure files or image files. 
- --
- ### Axis Bank Brochure Sample Used: [Axisbank.pdf](https://github.com/IWorkWonders/LogoAndTextDetector/files/2759675/Axisbank.pdf)
- ### HDFC Bank Brochure Sample Used:[HDFC.pdf](https://github.com/IWorkWonders/LogoAndTextDetector/files/2759676/HDFC.pdf)
---
- Now, the next step is to just place logo files in any Logo folder and PDF or image files in any repository folder. Provide the full path of each directories in the script.
- Add textual keywords to be searched (each separated by a semi-colon). 
- In this case I wish to search for 'axis' and 'hdfc', so I passed:  **"axis;hdfc"**.
- Run the script! If you dont pass a "Report folder", the script would automatically create the report in your default **User folder**.
- Script runtime is directly proportional:
-- Number of pages in each PDF file, 
-- Number of images being processed,
-- CPU/GPU computational power,
-- Orientation correction of text in images (if the text is tilted)
-- Image resolution in DPI. (You can set it to higher, if you have better computational power and a GPU.)

## Results:
- Excel based report is created.
- A log file is created.
- Conversion images with resulting detections is stored in a folder.
- As below: 
![screen_reportstructure](https://user-images.githubusercontent.com/41651749/51182250-8e98aa00-18f3-11e9-9e6f-78ec17bfcd99.png)
- This is how the excel report looks. 
![screen_reportexcel](https://user-images.githubusercontent.com/41651749/51182448-42019e80-18f4-11e9-9c9b-03b898f858a0.png)
- Look at the **"MIN MATCH COUNT GIVEN"**, this decides how many minimum matches should be considered in order to get the detection listed on the report. 
- Look at the **"KEYWORDS TO DETECT"**, this is the textual keywords, passed in order to get it detected. 
- There was an errored out row as well, during the processing which has been caught during in the report as below. Giving us an opportunity to look at the **"Log File"**.

- ![screen_reportexcelerror](https://user-images.githubusercontent.com/41651749/51182447-42019e80-18f4-11e9-9517-e5250f08b087.png)
- Some how there was a problem with a return value, (on which I will work post this ReadMe update) 
- ![errorlog](https://user-images.githubusercontent.com/41651749/51183866-8ee77400-18f8-11e9-9920-056cd50a7284.png)
- The log file helps in understanding what went wrong, and yet keeps the program execution in progress when an error is encountered. 

---
## Results: 
---
### Sample Result - HDFC BANK : [Logo Detection]

![res_key_hdfc_full___conv_-000002](https://user-images.githubusercontent.com/41651749/51187042-fd303480-1900-11e9-993e-8db791e219d0.png)
![res_key_hdfc_full___conv_-000003](https://user-images.githubusercontent.com/41651749/51187043-fd303480-1900-11e9-8a36-fec763d09275.png)
![res_key_hdfc_full___conv_-000010](https://user-images.githubusercontent.com/41651749/51187044-fd303480-1900-11e9-9d7b-63fa9bb09851.png)
![res_key_hdfc_full___conv_-000001](https://user-images.githubusercontent.com/41651749/51187045-fdc8cb00-1900-11e9-8060-c2e8ce50e06e.png)

---
### Sample Result - AXIS BANK : [Logo Detection]

![res_key_axislogofull___conv_-000004](https://user-images.githubusercontent.com/41651749/51187831-b2172100-1902-11e9-92ed-a9f399de6a90.png)
![res_key_axislogofull___conv_-000005](https://user-images.githubusercontent.com/41651749/51187833-b2afb780-1902-11e9-9d8c-ed727835a805.png)
![res_key_axislogofull___conv_-000001](https://user-images.githubusercontent.com/41651749/51187834-b2afb780-1902-11e9-9d61-d07c3ddd4478.png)
![res_key_axislogofull___conv_-000002](https://user-images.githubusercontent.com/41651749/51187837-b3484e00-1902-11e9-85ae-38c621a8e4f0.png)
![res_key_axislogofull___conv_-000003](https://user-images.githubusercontent.com/41651749/51187838-b3484e00-1902-11e9-8872-3864c29788e5.png)

---
### Sample Result - HDFC BANK : [Textual Keyword Detection]

![conv_-000001_text_detection_result](https://user-images.githubusercontent.com/41651749/51188748-914fcb00-1904-11e9-864e-68e75e27a681.png)
![conv_-000003_text_detection_result](https://user-images.githubusercontent.com/41651749/51188750-9280f800-1904-11e9-817c-6e3ec8345eb7.png)
![conv_-000002_text_detection_result](https://user-images.githubusercontent.com/41651749/51188749-91e86180-1904-11e9-9de8-6d131d160e55.png)

---
### Sample Result - AXIS BANK : [Textual Keyword Detection]

![conv_-000002_text_detection_result](https://user-images.githubusercontent.com/41651749/51187999-0ae6b980-1903-11e9-929d-39648aac7fdb.png)
![conv_-000003_text_detection_result](https://user-images.githubusercontent.com/41651749/51188001-0ae6b980-1903-11e9-844f-a2d22e2bd47d.png)
![conv_-000004_text_detection_result](https://user-images.githubusercontent.com/41651749/51188003-0b7f5000-1903-11e9-9f5f-004134dbdd83.png)
![conv_-000005_text_detection_result](https://user-images.githubusercontent.com/41651749/51187998-0ae6b980-1903-11e9-8019-d4fc4e80bf1f.png)



#### Points To Note: 
- At some instances, the textual detection was missed, however, we make up for it in the Logo detection, if you look closely in the above result images, and similarly vice versa. 
- Artificial intelligence has not yet advanced to get results with 100% confidence/accuracy, in pattern recognition or image text extraction. Hence, such measures to increase accuracy.




## Look forward for more updates on this project. Planning to add other logo and text detection techniques.

---



# Other projects I am working on includes:
- Optical Character Recognition of PDF files/Images.
- Natural Language ToolKit, Sentiment Analysis for Marketing.
- Sentiment Analysis for enhancing customer care experience.
- Facial recognition and detection in PDF Files.
- Face ID implementation.
- Face Emotion detection.
- Data visualization.


# For customizing the solution to meet your needs, contact me @:
- Email @ [IWorkWondersLabs@gmail.com]
- Leave a note here.
- Available for contracts, customization, consultation & hire.
- For live customized demonstrations, please drop an email.
