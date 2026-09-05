# RegDiff: Characterizing Cross-Regional Differences in Privacy Regulations and App Privacy Practices

This code is the official implementation of RegDiff.

# About

We propose RegDiff to understand the correlation between differences in privacy practices and differences in regional privacy regulations. RegDiff compares regional regulations, regional privacy policies, and regional behavior disclosures in the clause-region space, and then analyzes the correlation between regional regulatory differences and privacy practice differences.

# Dependencies

```text
python
apktool
openai
```

# Usage

## Perform Main Experiments

### Privacy Policy Construction

1. Decompile the APK.  
   Use the following command in the Windows terminal, for example:
   ```text
   apktool.bat d D:\com.jvstudios.gpstracker-254.apk
   ```

2. Search for privacy policy links in the APK.  
   Run:
   ```text
   readapkcode_pp.ipynb
   ```

3. Process the privacy policy links.  
   Run:
   ```text
   ppjosn_deplicated.ipynb
   ```

4. Use `utool` to generate the APK version summary file.  
   Run:
   ```text
   utool.ipynb
   ```

5. Use OpenAI to identify the final privacy policy link from the candidates.  
   Run:
   ```text
   openai_pp_url.ipynb
   ```

6. Download the privacy policy from the Wayback Machine.  
   Run:
   ```text
   waybachmachine_find_pp_url_download_md.ipynb
   ```

7. Download the privacy policy from the APK itself.  
   Run:
   ```text
   framwork\download_apkitself_link_md.ipynb
   ```

8. Download the privacy policy from Google Play.  
   Run:
   ```text
   framwork\static_googleplay_link_download_md.ipynb
   ```

9. Process the downloaded results.  
   Run:
   ```text
   utool.ipynb
   ```

10. Download privacy policies from two sources and process the results.  
    Run:
    ```text
    framwork\download_pp_link_md.ipynb
    framwork\process_md.ipynb
    ```

### Clause Classification in Privacy Policies

1. Perform two-stage classification.  
   Run:
   ```text
   framwork\openai_clasues_pp_txt.ipynb
   ```

2. Process the classification results.  
   Run:
   ```text
   framwork\openai_clasues_pp_txt_process.ipynb
   ```

3. Generate region information.  
   Run:
   ```text
   utool.ipynb
   ```

4. Construct the privacy policy matrix.  
   Run:
   ```text
   framwork\openai_openai_clasues_pp_maaping_matrix.ipynb
   ```

### Process Behavior Documents

1. Generate the APK name list file.  
   Run:
   ```text
   framwork\openai_openai_clasues_pp_maaping_matrix.ipynb
   ```

2. Generate region information.  
   Run:
   ```text
   framwork\geodiff_version_mapping_tool.ipynb
   ```

### Clause Classification in Behavior Documents

1. Perform two-stage classification.  
   Run:
   ```text
   framwork\geodiff_version_mapping.ipynb
   ```

2. Construct the behavior matrix.  
   Run:
   ```text
   framwork\geodiff_version_mapping_matrix.ipynb
   ```

### Analyze Privacy Practices and Regulations

1. Analyze regulatory differences.  
   Run:
   ```text
   Evaluation\analysis_R.ipynb
   ```

2. Analyze privacy policy differences.  
   Run:
   ```text
   Evaluation\analysis_PP.ipynb
   ```

3. Analyze privacy policy differences in relation to regional regulatory differences.  
   Run:
   ```text
   Evaluation\analysis_PP2_alignment.ipynb
   ```

4. Analyze behavior differences.  
   Run:
   ```text
   Evaluation\analysis_B.ipynb
   ```

5. Analyze behavior differences in relation to regional regulatory differences.  
   Run:
   ```text
   Evaluation\analysis_B_alignment.ipynb
   ```
