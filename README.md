# Grade 3 Hindi (G3H) Dataset

This dataset will be released as part of the ICASSP 2027 research paper titled "Hindi Oral Reading Miscue Detection with Semi-supervised Fine-tuning". 

## Dataset details
The dataset contains audio recordings and text transcripts of 1908 utterances of read aloud text across 1036 unique speakers. These audios were collected as part of a benchmarking exercise in December 2023 for testing reading levels in Grades 3 students across a government school network predominantly from the North Indian Hindi speaking states on Hindi level-appropriate texts. The [text prompts](#text-prompts) which comprise of 3 stories of 2 paragraphs each have also been provided. The total audio duration of the dataset is 21.3 hours with speakers uniformly distributed across the three stories. The dataset is fully labeled with filler/non-speech events and word-level transcriptions using a [semi-automated transcription process](#manual-transcription-process).

Ethics clearance was obtained for the audio recording with anonymised speaker information. The students, who come with diverse home languages, are introduced to both Hindi and English reading and writing in Grade 1.

## Text Prompts
The grade-appropriate text passages were chosen by a working group of teachers from the government school network from Open Content sources such as [Panchatantra](https://en.wikipedia.org/wiki/Panchatantra) and [Story Weaver](https://storyweaver.org.in/en). The 3 passages chosen for Grade 3 are given below. Note that each story has been split up into 2 paragraphs of 50-70 words each.

### Story 1: **जूता** (ID: HI-G3H-001, 138 words)

एक राजा था। उसका एक बड़ा-सा राज्य था। एक दिन उसे देश घूमने का विचार आया और उसने देश भ्रमण की योजना बनाई और घूमने निकल पड़ा। जब वह यात्रा से लौट कर अपने महल आया, उसने अपने मंत्रियों से पैरों में दर्द होने की शिकायत की। राजा का कहना था कि मार्ग में जो कंकड़-पत्थर थे, वे मेरे पैरों में चुभ गए और इसके लिए कुछ इंतजाम करना चाहिए।

कुछ देर विचार करने के बाद उसने अपने सैनिकों व मंत्रियों को आदेश दिया कि देश की संपूर्ण सड़कें चमड़े से ढक दी जाएं। राजा का ऐसा आदेश सुनकर सब सकते में आ गए। लेकिन किसी ने भी मना करने की हिम्मत नहीं दिखाई। यह तो निश्चित ही था कि इस काम के लिए बहुत सारे रुपए की जरूरत थी। लेकिन फिर भी किसी ने कुछ नहीं कहा।

### Story 2: **भूखी चिड़िया** (ID: HI-G3H-002, 132 words)

सालों पहले एक घंटाघर में टींकू चिड़िया अपने माता-पिता और पाँच भाइयों के साथ रहती थी। टींकू चिड़िया छोटी सी थी। उसके पंख मुलायम थे। उसकी माँ ने उसे घंटाघर की ताल पर चहकना सिखाया था। घंटाघर के पास ही एक घर था, जिसमें पक्षियों से प्यार करने वाली एक महिला रहती थी। वह टींकू चिड़िया और उसके परिवार के लिए रोज रोटी का टुकड़ा डालती थी।

एक दिन वह बीमार पड़ गई और उसकी मौत हो गई। टींकू चिड़िया और उसका पूरा परिवार उस औरत के खाने पर निर्भर था। अब उनके पास खाने के लिए कुछ नहीं था और न ही वो अपने लिए खाना जुटाने के लिए कुछ करते हैं। एक दिन भूख से बेहाल होने पर टींकू चिड़िया के पिता ने कीड़ों का शिकार करने का फैसला किया।

### Story 3: **कहानियों का शहरा** (ID: HI-G3H-003, 119 words)

मीमी एक छोटी सी लड़की थी जो एक भीड़-भाड़ वाले शहर में रहती थी। उसे कहानियाँ बहुत पसंद थीं, पर उसे कहानियाँ सुनाने के लिए किसी के पास समय नहीं था। मीमी ने जिससे भी कहानियाँ सुनाने की बात कही, उनके पास कहानियाँ सुनाने की फ़ुर्सत नहीं थी। किसी के पास मीमी के लिए समय नहीं था। कहानियों के लिए तो बिल्कुल नहीं।

एक दिन दीदी मीमी के स्कूल आईं। दीदी टीचर नहीं थीं और वे पढ़ती भी नहीं थीं। वे बच्चों से तो बड़ी थीं लेकिन टीचर से छोटी ही थीं। दुबली पतली सी, चमकीली आँखें। चेहरे पर हल्की सी मुस्कान। दीदी रोज़ स्कूल आने लगीं और बच्चों की दोस्त बन गईं और टीचर की भी।


## Manual transcription process

The procedure for manual transcription is as follows:

The collected audio recordings are first passed through an in-house ASR [Kaldi TDNN with Language Model trained on the text prompts and a garbage model] to get the decoded text. Using the alignment of the decoded text with the text prompts and further using the time-stamps, sentence-level transcripts are created in an Audacity label track format. The audio and the label track are then opened in Audacity by the transcriber for sentence level transcription. The transcribers are expected to label each word based on what they perceive as uttered in the audio. They type in Devanagari (phonetic alphabet easily convertible to phone symbols) using the Microsoft’s Indic Language Input Tool (ILIT) installed on the transcriber’s machine. Additionally, the transcriber is trained to use the following labels for certain common events encountered in the recordings. 

| Transcription Label | Description |
| --- | --- |
| SIL  | Silence (>200ms)  |
| BR  | Breath (inhalation/exhalation), sniffling |
| ON  | Other noise appearing in isolation e.g. Noise of birds, mobile, vehicles, bell, mic noise, clearing of throat   |
| FP  | Filled pauses like uh, hmm, umm, etc.  |
| IR  | Irrelevant speech (background speaker) present at the start or end of the recording   |
| MB  | Unintelligible words or mumbling  |
| WH  | Child whispering a word (many a times this can be heard when the child is trying to spell out the word)  |
| HS  | Hesitation while uttering a word. It is used as a suffix for words where the child hesitated while reading.  |

The completed transcriptions are further quality-checked by an expert who is comfortable with both spoken Hindi and Devanagari orthography and is aware of the labelling conventions. These non-speech labels are retained in the raw transcription files but are removed during the preprocessing step. Before phone-level scoring, only the actual word tokens are passed to the lexicon for phone sequence generation.

## Contents of the repository
- `references` folder contains the M.S. Thesis of Raj Gothi et. al. referred to in the paper.

For further details, check out the following link: [Supplementary material](https://app.notion.com/p/Supplementary-material-Interspeech-submission-38eda16c0a0080ed941ad4fd55f68b98)
