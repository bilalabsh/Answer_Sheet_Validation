# Answer Sheet Validation

Grades handwritten exam answers automatically. Upload a student's answer sheet (images or PDF) and the marking scheme (DOCX or PDF), and the tool reads the handwriting and assesses each answer against the scheme.

## How it works

1. **Pre-processing:** answer sheet images are cleaned up with OpenCV, and PDFs are split into page images with PyMuPDF
2. **Reading handwriting:** pages are sent to the Llama 3.2 90B Vision model (via Groq) to extract the student's answers
3. **Marking scheme:** extracted from the DOCX or PDF the teacher uploads
4. **Assessment:** the model compares each answer with the marking scheme and returns marks with feedback

## Tech stack

Python · Groq (Llama 3.2 Vision) · OpenCV · PyMuPDF · python-docx · Streamlit

## Run it

```bash
pip install -r requirements.txt
# add GROQ_API_KEY to a .env file (never commit it)
streamlit run app.py
```
