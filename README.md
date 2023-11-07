# TPISS

This repository provides a framework for predicting irregularly sampled sequence data. For this project, customer journey data is used. 

First, open the files in Google Drive as these files are intended for use in Google Collab. Change the PATH to your path in your Google Drive. 
The required libraries are pre-defined per file and installed in the file itself too. To download the Dunnhumby - The Complete Journey dataset, click here: https://www.kaggle.com/datasets/frtgnn/dunnhumby-the-complete-journey. Put the dataset in a map called "output_other_dataset"

Preprocessing the hotel dataset:

To find the dataset that preprocesses the dataset run file: preprocess_data_full_hotel_dataset_final.ipynb

The different forms of datasets:
-	Leisure dataset (RQ5): leisure_hotel_dataset_final.ipynb
-	Business dataset (RQ5): business_hotel_dataset_final.ipynb
-	Balanced I dataset (RQ6): balanced_I_hotel_dataset_final.ipynb
-	Balanced II dataset (RQ6): balanced_II_hotel_dataset_final.ipynb

Different models to find the best-performing one for the framework (RQ3):
-	TFT: Run TFT_creation_to_creation_final.ipynb with model: booking_time_final_original/trial_4/epoch=19-v1.ckpt
-	TransformerEncoder: Run transformer_encoder_final.ipynb
-	LSTM: Run LSTM_next_final.ipynb
    - To run the different datasets:
        - Original: Datasets used:output/10_selected_guest_data/df_original_data_standardscaler and output/10_selected_guest_data/y_original_data with batch size 512
        -	Business: output/10_selected_guest_data/df_business_data_standardscaler and output/10_selected_guest_data/y_business_data with batch size 64
        - Leisure: output/10_selected_guest_data/df_leisure_data_standardscaler and output/10_selected_guest_data/y_leisure_data with batch size 256
        - Balanced I: output/10_selected_guest_data/df_balancedI_data_standardscaler and output/10_selected_guest_data/y_balancedI_data with batch size 256
        - Balanced II: output/10_selected_guest_data/df_balancedII_data_standardscaler and output/10_selected_guest_data/y_balancedII_data with batch size 256
-	RFR: Run RandomForestRegressor_final.ipynb. The same datasets hold for the one stated above for LSTM.
  
To compare the framework to the Dunnhumby - The Complete Journey dataset (RQ8):
-	Preprocessing dataset: Run Preprocess_data_dunnhumby.ipynb
-	Baseline: Run RandomForestRegressor_final_dunnhumby.ipynb
-	LSTM: Run LSTM_final_dunnhumby.ipynb
  
To run the files containing the business value of this thesis (RQ4 and RQ7):
-	Prediction income hotel with TFT model: Run TFT_target_price_final.ipynb with model: price_tft/trial_9/epoch=19.ckpt
-	Last event of bookers prediction with LSTM: Run LSTM_stop_final.ipynb
  
To run the files for ablation analysis on LSTM:
-	Last event:
    -	Ablation on LSTM: Run LSTM_stop_final_ablation.ipynb
    -	Ablation on last event net: Run LSTM_stop_final_ablation.ipynb and set stop_net to False in the model
    -	Ablation on embedding net: Run LSTM_stop_final_ablation.ipynb and set embedding to False in the model
-	Next event:
    -	Ablation on LSTM: Run LSTM_next_final_ablation.ipynb
    -	Ablation on next event net: Run LSTM_next_final_ablation.ipynb and set next_event_net to False in the model
    -	Ablation on embedding net: Run LSTM_next_final_ablation.ipynb and set embedding to False in the model
      
Sources that have been utilized are the PyTorch tutorials and SHAP tutorials. 
