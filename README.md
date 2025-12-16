*Azure Data Factory – Credit Card Data Flow Implementation*

*Overview*

This is a beginner-friendly Azure Data Factory project created to understand how Mapping Data Flows work by transforming and routing credit card data in a simple pipeline.

*Dataset*

The input dataset is a CSV file stored in Azure Data Lake Storage, containing:

	•	Credit ID
	•	Card Type (Master / Visa)
	•	Card Name
	•	Credit Score

*Data Flow Logic*

The following steps were implemented using ADF Mapping Data Flows:

	•	Source – Read credit card data from ADLS (input container)
	•	Select – Removed the Credit ID column as it was not required for downstream processing
	•	Derived Column – Added a discount column based on card type
	  	Master → 20%
	  	visa → 10%
	•	Conditional Split – Separated records into Master and Visa data streams
	•	Sort – Sorted each stream by credit score (descending)
	•	Sink –
	   	Master data written to the Master container
	   	Visa data written to the Visa container
	   	Output configured as single files

*Pipeline & Trigger*

	•	The Mapping Data Flow is executed through an ADF Pipeline
	•	A schedule trigger is configured to run the pipeline every Tuesday

*Tools & Services Used*

	•	Azure Data Factory
	•	Mapping Data Flows
	•	Azure Data Lake Storage Gen2

*Outcome*

This project gave me a strong starting point with Azure Data Factory Mapping Data Flows, helping me understand how data is transformed, split, sorted, and orchestrated within a pipeline.
