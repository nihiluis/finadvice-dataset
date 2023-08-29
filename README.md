# Financial advisor dataset
With the dataset the LLM takes the role of an advisor giving financial advice to a user.

This repo contains notebooks on generating a synthetic dataset (100 GPT-4 answers for 100 Reddit submissions from /r/personalfinance) as well as [training](FinAdv100Train.ipynb) and [inference](InferenceSimplified.ipynb) of the resulting model (based on Llama2 7B). The training can be performed on a free T4 GPU on Colab (with 4-bit QLoRa quantization).

The results are available on Huggingface: [Model](https://huggingface.co/nihiluis/financial-advisor-llama-7b) and [Dataset](https://huggingface.co/datasets/nihiluis/financial-advisor-100)

## Disclaimer
This is just a proof-of-concept for research and education purposes to test another use case for homegrown LLaMa2 models. For actual use, as for most fine-tunings, ChatGPT3 and 4 will yield better results and are cheaper to setup.

## Credits
This repo adapts code from the following resources:

[Llama1 7B fine-tuning with QLoRA + Adapter merge + EOS token to avoid repetitions](https://georgesung.github.io/ai/qlora-ift/)
[Falcon 7B fine-tuning with QLoRa... + Bitsandbytes on a 137 sample dataset](https://medium.com/@iamarunbrahma/fine-tuning-of-falcon-7b-large-language-model-using-qlora-on-mental-health-dataset-aa290eb6ec85)
[Merging QLoRA adapter weights gist][https://gist.github.com/ChrisHayduk/1a53463331f52dca205e55982baf9930]

## Example prompt and completion
This example (recent reddit submission taken from /r/personalfinance) is not cherry-picked and may give you an impression what can be expected from a 7B Llama2 model.

### Human
So, I made a paypal account and set my age as 18 when I was like 11. (I'm 15 now.) I didn't enter any information and only used it to put gift cards onto. When I was 13, I added my card to it that I got with BOFA. Then I signed up for a website subscription trial, and canceled it before it charged me, except that it didn't cancel because my service cut so they charged me the 30$. Afterwards, I realized and canceled it properly, but I wasn't aware I had a limited amount of time to pay it, or that I had to pay it at all. This was in March. Today I woke up to a letter from ACI (paypal's debt collection agency I think??) That says I have to pay it by September 28th, but my mom refuses to help me and won't explain any of it, telling me that this is a good time to learn on my own because she had to at 18, and that she won't explain it, and I don't understand how or what I'm supposed to do. Paypal locked my account so I can't log in to pay it. 've been freaking out about this for hours, what should I do?

### Assistant
I'm sorry to hear about your situation. Here are some steps you can take:

1. **Contact PayPal Support:** You can contact PayPal's customer service directly. They can help you unlock your account and potentially work out a payment plan for the debt. Make sure to keep a record of all communication with them.
2. **Gather All Relevant Information:** If possible, try to gather all the correspondence you've received from ACI and PayPal regarding this debt. This will help you understand your rights and options.
3. **Seek Legal Advice:** If the debt is significant, you may want to consider seeking legal advice. A lawyer can help you understand your rights and potential options, including the possibility of having the debt declared invalid.
4. **Contact Your Bank:** If the debt was charged to your BOFA card, you may be able to dispute the transaction. Banks are required to uphold certain laws regarding underage transactions.
5. **Contact the Credit Bureau:** If the transaction was reported to the credit bureaus, you can dispute it there as well. This can impact your credit score, so it's important to understand how it will affect you.
6. **Seek Emotional Support:** This can be a stressful situation, and it's important to have someone to talk to who understands what you're going through. Consider talking to a trusted friend or family member, a counselor, or a hotline like the National Youth Crisis Line (724-986-KIDS).
 
Remember, you have rights as a consumer, even if you made some mistakes as a minor. It's important to understand your responsibilities as well, but you should not be held accountable for more than you can reasonably afford. If you can't pay the debt in full, you may be able to negotiate a payment plan. Always communicate clearly and document all your interactions.<eos_token>[...]