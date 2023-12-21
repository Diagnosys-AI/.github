# Diagnosys AI

Welcome to Diagnosys AI. Diagnosys AI proposes a tool tailored and aimed at the UK's junior doctors - F1's, F2's, and IMT1's (first stage of specialty training). Diagnosys AI is designed to alleviate the challenges of diagnostic uncertainty and efficiency that junior doctors frequently encounter. Our solution focuses on streamlining the diagnostic process, enhancing decision-making, and ultimately contributing to better patient outcomes.

![Diagnosys Frontend](./img/Screenshot%20from%202023-12-21%2012-45-49.png)

This RAG app is enhanced with [TruLens](https://github.com/truera/trulens). TruLens-Eval is used for performance evaluation.

![TruLens Eval](./img/Screenshot%20from%202023-12-21%2012-47-41.png)

The project is deployed [here](https://diagnosys-ai.vercel.app/). Note that this is a demo version, and is not connected to the backend.

## Features

- It uses Gemini AI by Google DeepMind - It is a groundbreaking multimodal AI model that seamlessly integrates text, code, audio, image, and video.

## Business Case

### Problem

From discussions, there seems to be some degree of diagnostic uncertainty in medicine, once the history is taken. Sometimes, when things are very busy, some investigations are missed out. Hospitals are short staffed as they are, and sometimes, even when things are busy, F1's, F2's and IMT1's need to run diagnoses by the registrar (who may not even be available) if there is any uncertainty. An AI could fit in here to validate diagnoses.

On a shift, doctors don't have time to go through every potential diagnosis. One Doctor Interviewed said "Sometimes I have no idea whats going on". He went on to say, "The amount of times I've taken a history and forgotten to check one thing and had to go back to check". This lack of efficiency is the pain point that Diagnosys AI aims to address.

From a different perspective, there is a large number of people started on antibiotics just because of an unclear diagnosis. Take the [Sepsis Pathway](https://www.britishjournalofcommunitynursing.com/media/zdynyl4r/bjcn-2022-27-2-69_f01.jpg):

![Sepsis Pathway](./img/image.png)

Here, on step 3, if there are any Red Flags present on step 3. such as Systolic BP < 90 mmHg, you should start Antibiotics, even though that low BP could be due to a number of other things - a lot overlaps with Low Blood Pressure for example. This is where a Diagnosis AI could come in. It could quickly suggest potential diagnoses, and suggest further investigations, before we start Antbiotics. It could also suggest potential treatments. This will, in addition, help towards the Antibiotic Resistance Crisis.

### Proposed Solution

Use a MultiModal Retrieval-Augmented Generation (RAG) Stack, contexualised with best practice and resources (listed below) with an LLM (Gemini) to provide a comprehensive list of potential diagnoses, investigations and treatments. This will be a tool for Junior doctors, and will be input with the History taken from a patient. In the above process, it will fit in-between stage 3 and 4. In detail:

- Input (LLM be prompted with) History, Examinations done and (in the future) Patient Records
- Generate potential diagnoses and further investigation
- Specific things that could have been be missed out, as well as potential treatments
- Suggest potential examinations and what might be found in them i.e. What are red flags from suggested examinations to look out for
- Trust in the AI is a risk factor. This is mitigated by providing citations to the contextual information, such as Oxford Handbook of Clinical Medicine, Kumar & Clark's Clinical Medicine, etc.
- Can utilise multi=modal Models with Images, with rashes for example. These will refernece images from DermNet NZ

###

## Resources / Context Used:

- The Oxford Handbook of Clinical Medicine is a pocket textbook aimed at medical students and junior doctors, and covers all aspects of clinical medicine.
- Kumar & Clark's Clinical Medicine - Textbook aimed at medical students in the preclinical years of study.
- DermNet NZ - DermNet NZ is a website dedicated to dermatology. It has a large collection of photos and information on skin conditions.
- NICE CKS - NICE guidelines are evidence-based recommendations for health and care in England. They set out the care and services suitable for most people with a specific condition or need, and people in particular circumstances or settings.

### Potential Added Benefits

- Can be used to help train Junior Doctors / Medical Students.
- This will also help towards the Antibiotic Resistance Crisis.
- Eventually, can be used to help patients self-diagnose, and know when to go to the GP (111 sucks balls).

### Risks & Challenges

- **Litigation and Reliability:** Clearly position Diagnosys AI as an assistive tool, not a replacement for medical judgment.
- **Data Privacy and Security:** Implement robust security measures to protect sensitive patient data.
- **Building Trust:** Trust in the AI is a critical risk factor. This is mitigated by providing citations to the contextual information, such as Oxford Handbook of Clinical Medicine, Kumar & Clark's Clinical Medicine, etc.

## Links

- [Hackathon Info](https://lablab.ai/event/gemini-ai-hackathon)
- [LlamaIndex: a Data Framework for LLM Applications](https://lablab.ai/tech/llamaindex)
  - [GitHub](https://github.com/run-llama/llama_index)
- [TruLens Notebook](https://github.com/truera/trulens/blob/main/trulens_eval%2Fexamples%2Fexpositional%2Fmodels%2Fgoogle_vertex_quickstart.ipynb)
- [Gemini Notebook](https://colab.research.google.com/drive/11b6-GvwIXB5r_qsoLAYEa6ejIPUoC2hw)
- [Multi-Modal LLM using Google's Gemini model for image understanding and build](https://colab.research.google.com/github/run-llama/llama_index/blob/main/docs/examples/multi_modal/gemini.ipynb)
- [Gemini Example](https://colab.research.google.com/drive/1W5UkUpjNK9wi7RzuEv83vC0ejBgJ5Ty3?usp=sharing)

## Educational Materials

Resources that will familiarize you with Gemini AI

- [Gemini AI Documentation](https://ai.google.dev/docs)
- [Test and Get Started with Gemini AI on Google Cloud Vertex AI](https://console.cloud.google.com/vertex-ai/generative/multimodal/prompt-examples/Extract%20text%20from%20images?project=wdll-252515)
- [Gemini Multimodal Prompting Guide](https://developers.googleblog.com/2023/12/how-its-made-gemini-multimodal-prompting.html)
- [Video Guide from Sam Witteveen: Getting Started with Gemini Pro on Google AI Studio](https://www.youtube.com/watch?v=HN96QDFBD0g)
- [TruLens Evaluating Multi-Modal RAG Notebook](https://github.com/truera/trulens/blob/main/trulens_eval%2Fexamples%2Fexpositional%2Fframeworks%2Fllama_index%2Fllama_index_multimodal.ipynb)
- [RAG App in Production Blog](https://blog.llamaindex.ai/shipping-your-retrieval-augmented-generation-app-to-production-with-create-llama-7bbe43b6287d)
- [Advanced Multi-Modal Retrieval using GPT4V and Multi-Modal Index/Retriever](https://github.com/run-llama/llama_index/blob/main/docs/examples/multi_modal/gpt4v_multi_modal_retrieval.ipynb)
- [OpenAI Dashboard](https://platform.openai.com/account/limits)

## Starter Code

- [LLAMA Python](https://github.com/seldo/create-llama-python/blob/main/frontend/app/components/ui/chat/chat-input.tsx)

## Learn More

To learn more about LlamaIndex, take a look at the following resources:

- [LlamaIndex Documentation](https://docs.llamaindex.ai) - learn about LlamaIndex (Python features).
- [LlamaIndexTS Documentation](https://ts.llamaindex.ai) - learn about LlamaIndex (Typescript features).
