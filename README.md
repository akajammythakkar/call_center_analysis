# Call Recording Analysis

This notebook demonstrates how to analyze call recordings using the Gemini API to extract structured information and evaluate call center executives.

## Setup

1.  **Install Dependencies:** Run the first code cell to install the necessary libraries (`google-genai`).

2.  **API Key:** Obtain a Gemini API key from Google AI Studio. Add this key to the Colab Secrets manager with the name `GEMINI_KEY`.

3.  **Upload Data:** Upload your zip file containing call recordings (e.g., `Call Recordings-20250825T130307Z-1-001.zip`) to your Colab environment.

4.  **Unzip Recordings:** Run the code cells to remove any previous `cr` directory and unzip your call recordings into a directory named `cr`.

## Analysis

The notebook performs the following steps:

1.  **Define Analysis Function:** The `generate` function is defined to interact with the Gemini API, sending the audio file and a detailed prompt to extract structured data about the call.

2.  **List Audio Files:** The notebook identifies all `.wav` files within the unzipped `cr` directory.

3.  **Process Recordings:** It iterates through each audio file, calls the `generate` function to analyze the recording using the Gemini API, and stores the results. The results are also written to a text file (`file.txt`).

4.  **Flatten Results:** The extracted JSON data is flattened into a format suitable for a pandas DataFrame.

5.  **Create DataFrame and Export:** The flattened data is loaded into a pandas DataFrame. The file paths are cleaned, and the DataFrame is then exported to both CSV (`call_analysis_1.csv`) and Excel (`call_analysis_1.xlsx`) formats.

## Output

The final output is a pandas DataFrame and exported CSV and Excel files containing the structured analysis of each call recording, including:

-   File Path
-   Industry Domain
-   Call Type (Inbound/Outbound)
-   Call Timing Details (Total, Customer Speaking, Executive Speaking, Wait Time)
-   Call Summary (Query, Resolution Stated, Resolution Time Suggested)
-   Executive Rating (Politeness, Language Clarity, Adherence)
-   Participant Details (Name, Role, Gender, Language)

This structured data can be further analyzed and visualized to gain insights into call center performance and customer interactions.
