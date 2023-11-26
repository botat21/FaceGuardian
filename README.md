# FaceGuardian
Today, most KYC systems are instructed to consider specific features of the video when deciding wheter a video is real or rendered (such as eyes, lipsync alignment, and distinctions between the individual and the background). Consequently, these systems need constant development, and even then they are relatively easy to fool with modern DeepFake algorithms.

We designed an intelligent system that autonomously learns evaluation techniques, eliminating the need of specifying the details that it should look for. 

Banks with integrated KYC verification have large databases of previously authenticated customers, typically verified by human oversight, serving as great real samples. The challenge lies in generating synthetic samples, for which we developed a state of the art generator network leveraging existing generator algorithms, which is learning to produce more and more realistic deepfakes.

But how do we make the decisions? Well, we made a discriminator network competing with the generator. This way, both of our networks are learning continuously from each others’ strengths and weaknesses, without the need of manually configuring the most vulnerable features. This mirrors the strategy employed by antivirus software, wherein, when a new threat emerges, the algorithm adapts by devising a novel defense mechanism.

The model additionally expresses its confidence regarding the authenticity of the video. In cases where the model lacks sufficient confidence in its results, it can assign straightforward personalized tasks, such as displaying a number using hand gestures. This is particularly useful as generative models often struggle with synthesizing realistic hand representations. Videos falling below a specified confidence threshold are then subjected to more thorough inspection.
