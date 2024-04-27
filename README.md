# Attention Dilution and 
This project evaluates how the integration of varying amounts of contextual information affects the accuracy of a language model trained on the LIAR dataset, which is really important for identifying misinformation. By examining the model's performance on truthfulness classification tasks, I hope to ultimately enhance its utility in monitoring and mitigating the spread of misinformation online.

## Project PI
Paul Kramer, paul.kramer.1@vanderbilt.edu, kramerp

## Project Proposal

### Description of Problem/Opportunity
The problem at hand is the potential decline in the performance of LLMs when processing large amounts of context - potentially indicative of attention dilution. The opportunity lies in better understanding this behavior to improve the robustness and accuracy of models tasked with critical applications like detecting misinformation, particularly when utilizing datasets like LIAR that focus on the veracity of public statements.

### Proposed Solution/Approach
I hope to conduct a systematic analysis where the LLM's prediction accuracy is measured against increasing context sizes using the LIAR dataset - objective data. By plotting this relationship and employing statistical methods such as Spearman correlation and polynomial regression, I want to identify patterns that could indicate the presence of attention dilution. This will hopefully determine whether expanding the context aids or hampers the model's ability to discern truthfulness, which is crucial for its application in misinformation detection.

### Project Outline and Timeline
    Project Initialization and Planning (March 21-23)
        Define project scope.
        Outline research questions and objectives.

    Dataset Acquisition and Preprocessing (March 24-28)
        Obtain the LIAR dataset.
        Clean and preprocess the data for analysis.

    Model Selection and Setup (March 29-31)
        Choose an appropriate language model.
        Configure the model for the experiment.

    Preliminary Analysis (April 1-5)
        Run initial tests to establish baseline performance.
        Validate the experimental setup.

    Experimentation Phase I (April 6-10)
        Conduct experiments with varying context sizes (small to medium).

    Data Collection and Analysis I (April 11-13)
        Collect accuracy data from Phase I experiments.
        Perform initial statistical and visual analysis.

    Experimentation Phase II (April 14-18)
        Conduct experiments with larger context sizes.
        Address any issues from Phase I.

    Data Collection and Analysis II (April 19-21)
        Collect accuracy data from Phase II experiments.
        Extend statistical and visual analysis with new data.

    Results Synthesis and Report Drafting (April 22-24)
        Synthesize results from both experimentation phases.
        Draft the project report with findings and interpretations.

    Final Review and Submission (April 25-26)
        Review the draft report for accuracy and completeness.
        Make necessary revisions.
        Submit the final report.

## Goals of project 

Describe 1-5 goals of the project. 
### Determine the baseline accuracy of GPT-3.5-turbo on the LIAR dataset without additional context, establishing a benchmark for further test runs.

### Investigate how the model's accuracy changes as context size increases. To do this I'll adjust the amount of contextual information provided to the model and measure the resulting accuracy in truthfulness classification.

### Ultimately, explore the potential presence of attention dilution (or potentially overfitting) by identifying any trends where increasing context size does not continue to enhance or starts to degrade model performance.

## Project Metrics 
  
  The project should perform at least four different types of statistical analyses (e.g., baseline accuracy calculation, Spearman correlation, moving average, polynomial regression). This metric evaluates the depth and variety of statistical methods applied to explore potential attention dilution.
  The project should examine a range of context sizes spanning from no context (0) up to a large context size (e.g., 250), as specified in the experiments. This metric assesses the comprehensiveness of the model testing across different scenarios.
  At least three different types of data visualizations must be provided (e.g., line graphs, scatter plots with polynomial regression, moving averages). This ensures the visual representation of data supports a clear understanding of the trends and patterns.
  The project should include a detailed interpretation of the results, particularly focusing on the implications of high p-values and any potential evidence (or lack thereof) of attention dilution. This metric evaluates the depth of analysis and understanding reflected in the discussion.

## Self-Evaluation
In this project, I set out to explore the effects of context size on the performance of GPT-3.5 Turbo when classifying the truthfulness of statements from the LIAR dataset. Initially, I established a baseline accuracy for the model without additional context, which served as a critical benchmark for subsequent tests. This initial step was successfully completed, providing a clear reference point for evaluating the influence of added context.

As I increased the context size incrementally, I meticulously recorded and analyzed how accuracy was affected. This methodical approach allowed me to map out a detailed relationship between context size and model performance. The data demonstrated various accuracy levels at different context sizes, indicating that additional context does not consistently enhance model performance. In fact, the visualization of this data through polynomial regression suggested that beyond a certain point, additional context ceased to significantly improve accuracy, which could be indicative of attention dilution.

To further probe this potential attention dilution, I employed two main metrics: statistical analysis of trends and entropy calculations of predicted labels. The Spearman correlation test yielded a correlation of 0.258 with a P-value of 0.538, suggesting a weak and statistically non-significant relationship. This result hinted that increased context does not reliably enhance accuracy, supporting the hypothesis of attention dilution. Additionally, I calculated the entropy of label distributions across context sizes to assess the model's prediction consistency. Higher entropy at larger context sizes suggested increasing uncertainty or inconsistency in the model’s predictions, reinforcing the notion that too much context might confuse the model rather than aid it.

Overall, while the project did not conclusively prove the presence of attention dilution due to the high P-value in the correlation analysis, the observed trends in the regression and entropy analyses provided valuable insights. These findings for me suggest that while attention dilution might be a factor, other elements such as model capacity and the specific nature of the context used also significantly influence performance. This exploration has highlighted the complex dynamics of machine learning models in processing natural language and underscores the need for further investigation into how contextual information is best utilized by AI in language tasks.

## Reflection on Learning
For me, this has all substantially enhanced my understanding of the challenges and complexities involved in the field of NLP and ML, particularly through the exploration of the effects of context size on model performance. Initially, the project aimed to investigate whether there is a phenomenon of "attention dilution" in AI models when provided with increasing amounts of contextual information. Specifically, using the GPT-3.5-turbo model and the LIAR dataset, the study was designed to measure how the inclusion of various amounts of past statements as context affects the model's accuracy in truthfulness classification tasks.

The primary method involved incrementally increasing the context size provided to the model during the prediction phase and recording the accuracy at each level. The results, plotted and analyzed through statistical methods, including Spearman correlation and polynomial regression, revealed a non-significant relationship between context size and accuracy, with a Spearman correlation coefficient of 0.258 and a P-value of 0.538. This indicates that there is no strong evidence to suggest that increasing context size systematically improves the model's performance.

This outcome suggests several potential explanations: the model might be experiencing attention dilution, where too much context leads to a diffusion of the model's focus across too many details, diluting its ability to discern the truthfulness of the main statement effectively. Alternatively, the model could be encountering issues akin to overfitting, where it becomes too aligned with the nuances of the training data included as context, reducing its generalizability to new, unseen examples.

Reflecting on these findings, it is clear that simply adding more data is not always beneficial for AI performance, particularly in complex tasks such as truthfulness classification. This has significant implications for how we train and deploy AI models in real-world applications, especially in sensitive areas such as news dissemination and misinformation monitoring. It challenges the common presumption that more data and context invariably lead to better AI performance, highlighting the need for a more nuanced approach to data integration in AI training and operation.

The project has also sparked a deeper interest in exploring other dimensions of model tuning and optimization to address these challenges. One promising area is the application of reinforcement learning (RL) techniques. In RL, an agent learns to make decisions by receiving rewards or penalties based on its actions. Applying RL in the context of tuning AI models for NLP tasks could involve developing mechanisms where the model dynamically adjusts its focus and weighting on various parts of the input data based on the success of its outputs, thus potentially mitigating the risks of attention dilution or overfitting.

Moreover, the concept of tuning models by proxy, where simpler models are used to explore and optimize parameters or architectures before full-scale application on more complex models, presents an intriguing method to refine model performance. This approach could help in identifying optimal context sizes and configurations without the computational and time costs associated with experimenting directly on more complex models like GPT-3.5.

These insights are guiding my academic and career trajectories towards deeper AI research. They underscore the importance of theoretical and practical understanding of how AI models interact with data and the external world. Moving forward, I plan to engage in advanced studies focused on the strategic application of machine learning techniques to enhance the reliability and efficiency of AI systems. The challenges highlighted by this project emphasize the need for innovative approaches to AI training, such as integrating domain-specific knowledge into model development and exploring adaptive learning techniques that adjust to the complexity of real-world data.

Overall, this project has not only equipped me with valuable technical skills in handling and analyzing large datasets with AI models but also fostered a critical understanding of the limitations and potential of current AI technologies. It has reinforced my commitment to pursuing a career in AI research, with a focus on developing robust, adaptable AI systems that can perform effectively across a variety of challenging real-world applications. This journey will undoubtedly involve continuous learning and adaptation, but the complexities uncovered in this project have only served to deepen my curiosity and resolve to contribute to this dynamic field.

## What's Next?
Across the board, this has all deepened my interest in AI research, particularly in understanding model behaviors such as attention dilution and overfitting. I hope to extend this research by exploring RL techniques that adapt dynamically to the success of model outputs, potentially mitigating attention dilution. Additionally, I aim to investigate model tuning by proxy, offering a cost-effective method for enhancing model accuracy and efficiency.

The insights gained from this project are not only academically enriching but also practically This experience itself has equipped me with advanced skills in data manipulation and analysis, critical for my future career in AI. Moving forward, I am eager to collaborate with experts and peers alike, aiming to refine these findings and share them through academic publications or conferences, contributing to broader AI research and application.

## Video Recording:
https://us06web.zoom.us/rec/share/wkKLtTHlLF9bOWij9gfD1137oUc3qkhpxmAAdw4ejgrKCRcz5uqDtm1uo8TXcCi-.cTdF4ICGoITRMWy1?startTime=1714198992000
Passcode: xWo5^cNT
