# Can AI Detect Pneumonia from Chest X-Rays? Testing Vision Models on Medical Images

*By Karan Patel G29080064*

---

## Introduction

Pneumonia remains one of the leading causes of hospitalization worldwide, and timely diagnosis is critical for patient survival. The standard clinical tool is the **chest X-ray (CXR)**, where radiologists look for opacities or infiltrates that suggest infection. While experts are highly skilled at interpreting these images, radiology services are not always available in under-resourced settings, making automated assistance tools appealing.

This motivated my experiment: **Can modern, general-purpose AI vision models — like Copilot, Bard, or GPT-4 with vision — correctly detect pneumonia from chest X-rays?**

Importantly, these are not specialized medical models; they are designed to recognize everyday objects, people, and scenes. Yet, with the recent trend of multimodal AI, I was curious to see whether such models could provide meaningful insights when shown medical images.

To test this, I created three scenarios representing different diagnostic challenges:

1. **Classic pneumonia vs. clear normal lungs**
2. **Subtle pneumonia (borderline or mild case)**
3. **Confounding cases (abnormal, but not pneumonia)**

In each case, I uploaded an image and asked the same simple question:
👉 *“Does this chest X-ray show pneumonia?”*

Below, I document the model’s responses and reflect on both successes and failures.

---

## Scenario 1: Clear Pneumonia vs. Clear Normal

In this first test, I wanted to know if AI could distinguish “textbook” pneumonia from a healthy chest.

* **Pneumonia Image:** A classic case with dense white infiltrates in the left lung.
* **Prompt:** *“Does this chest X-ray show pneumonia?”*
* **Model Response:** “Yes, this X-ray shows pneumonia. You can see hazy white areas in the lung field.”

Then I tested a **control image** of a normal chest X-ray:

* **Model Response:** “This looks normal. Both lungs are clear.”

✅ **Success:** The model performed well when the images were straightforward.

⚠️ **Reflection:** In real life, such “perfect” cases are rare. But this result shows that AI models can align with human intuition when abnormalities are large and obvious.

---

## Scenario 2: Subtle / Borderline Pneumonia

Here I pushed the AI further: could it recognize early pneumonia with faint opacities?

* **Image:** A mild case where only small cloudy patches were visible.
* **Prompt:** *“Does this chest X-ray show pneumonia?”*
* **Model Response:** “This X-ray may show early pneumonia, but it is difficult to be certain. It could also be normal.”

✅ **Positive aspect:** The model did not overclaim and acknowledged uncertainty — which is arguably safer in a medical context.

❌ **Limitation:** The hesitation makes it clinically unhelpful. A radiologist would look for subtle cues such as opacity distribution or compare with prior films, but the AI simply says “maybe.”

💡 **Hypothesis:** This weakness likely stems from the fact that general-purpose models are not trained on large sets of medical images. Subtle features in lungs are very different from the everyday images (cats, cars, landscapes) that make up most of their training.

---

## Scenario 3: Confounding Cases

Finally, I tested the AI on an **abnormal but non-pneumonia** case: an X-ray with an enlarged heart and a medical device visible.

* **Prompt:** *“Does this chest X-ray show pneumonia?”*
* **Model Response:** “Yes, this may be pneumonia. There are irregular areas that look like infection.”

❌ **Failure:** The model confused unrelated findings with pneumonia.

This suggests that the model treats any deviation from “normal” lungs as pneumonia, instead of truly understanding the pathology.

⚠️ **Critical point:** In clinical practice, false positives can be dangerous — leading to unnecessary antibiotics or missed underlying conditions.

---

## Discussion

These three scenarios reveal a consistent trend:

* **Scenario 1 (Clear cases):** AI can succeed when features are textbook obvious.
* **Scenario 2 (Subtle cases):** AI struggles with borderline findings, where radiologists would rely on experience and nuanced judgment.
* **Scenario 3 (Confounding cases):** AI misclassifies unrelated abnormalities, showing a lack of domain understanding.

The root issue is that general-purpose vision models **lack medical training**. They have not been exposed to the subtle spectrum of chest X-rays, so they either hedge (“maybe pneumonia”) or generalize incorrectly.

Yet, the experiment is still valuable. It highlights both the **promise** (AI can sometimes recognize pneumonia) and the **risk** (AI can be dangerously wrong).

---

## Conclusion

So, can general AI models detect pneumonia from chest X-rays?

* **Yes**, when the case is textbook clear.
* **Sometimes**, when the case is borderline, though the answers are vague.
* **No**, when other abnormalities confound the decision.

The experiment underscores a key lesson: **AI is not yet a radiologist.** Without domain-specific training and validation, these systems are unreliable for clinical diagnosis.

However, the future is promising. Specialized deep learning models (e.g., CNNs trained on tens of thousands of X-rays) have shown diagnostic accuracy rivaling experts in research studies. If integrated responsibly — with human oversight, bias checks, and regulatory approval — AI could one day help triage patients, flag urgent cases, and support doctors in resource-limited settings.

For now, though, these general-purpose models are best seen as **experimental assistants, not medical tools.**

