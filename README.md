# CART498_Assignment5
Assignment 5: Postcards from my jungle

## Description
For this assignment, we were tasked with creating a jungle website that displays 50 non-existent animals with names that are in an unidentified language. There is also 4 audio sounds of these imaginary creatures and 16 phrases in the alien language. The images, text, and audio are all AI generated. Rather than pursuing realism, the generated media embraces ambiguity and procedural variability. This assignment is a conglomeration of everything we've learned so far in CART-498. 

## Strategies for Training Models
The strategies employed for training the models were focused on computational efficiency and stylistic experimentation. Rather than fully retraining a model based on a selected dataset, I opted for a lightweight fine-tuning approach due to my hardware limitation and fast generation for exploration. 
For image generation, I utilized the pretrained latent diffusion model Stable Diffusion v1.5. I also used Low-Rank Adaptation (LoRA) to avoid incurring the computational cost of full network training. This essentially means that a small trainable adapter layer was modified by my training data while keeping the base model weights frozen. The training data I employed was the CIFAR-10 dataset. This collection contains low-resolution natural images of a large variety of animals. I selected it because it allowed the model to generate somewhat realistic beasts while keeping abstraction and stylized morphology. 
For text generation, I used GPT-2 to create 16 phrases and name each animal. This was not working very well in all honesty. I could not get it to generate made up words. 
For sound generation, the pretrained diffusion based model Stable Audio Open was used. This is a heavier model so it was more difficult to test different prompts and generated audio. However, this model seemed to have the most interesting results compared to smaller models I found on hugging face. 
Overall, I leveraged pretrained model capabilities and focused on selectively training only when stylistic intervention was required. 

## Prompting
For image generation, the prompting was comprised of 5 prompts that would be randomly selected. Each prompt describe creating creatures with bizarre features and anatomy. For the audio prompts, I decided to write 4 prompts that described different noises in an ecosystem (i.e. mating calls, ambient forest noise, wet noises, etc). Finally, for the text prompt, I wanted the model to create a fictitious language that had a semblance of grammar rules and linguistic logic. I provided a couple of examples for it to be based off, but it did not really work. I assume its because I used GPT-2, but it adds to the overall wackiness. 


## Improvements
For improvements to this assignment, I would have liked to create an individual audio for each animal in my zoo. I find that it could have made the project act more like a mysterious archive of these non-existent creatures. I would have also liked to work on the website design a bit more to fit the aesthetic of a secret website. 