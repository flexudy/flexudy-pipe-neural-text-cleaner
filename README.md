# Multi-Lingual Neural Text Cleaner
Text quality can greatly influence the predictions of neural networks. We atempt to build a model that can do minor cleaning tasks like math, citation and title detection, which can then be masked before any further processing.

We generated synthetic data from Wikipedia pages like this:

1. Used regular expressions and html tags to detect citations (although it covers only a few cases).
2. Used html tags to detect titles
3. For mathematical formulas, we first extract mathml tags, render the mathml formulas with Selenium browser and save them as screenshots, then use pytesseract to perform OCR on the screenshots. We couldn't find a better way to extract the formulas, because directly trying to extract from mathml is just too diffult and html parsers like beatiful soup do not return "formula-looking" text.

Although most math formulas are not very useful, the intuition here is that this data can be used as a start to train models that can detect math formulas and more from standard files, resulting in better NLP models.

The data folder has English, French and German files from various fields of study. (Do not get fooled by the suffix on the file name. We recommend you do language detection to identify the respective languages.)

I included 100 files as .txt and the rest ~4300 are compressed in 3 parts (scroll at the bottom of /data to find them).
