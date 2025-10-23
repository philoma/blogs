# blogs

Why use Softmax with Categorical Cross-Entropy, and NOT Sigmoid?
Let’s break it down simply and clearly.


🚦 Softmax vs Sigmoid — Why Softmax Wins in Multi-Class
Feature	      Sigmoid  	                                Softmax
Output Range	0 to 1	                                  0 to 1
Sum of Outputs	❌ Not necessarily 1	                  ✅ Always = 1
Class Type	Multi-label (independent classes)          	Multi-class (1 correct class)
Best For	"Is it A? Is it B?" (multiple yes/no)	        "Which 1 class is correct?"

🎯 In Multi-Class Classification (only one correct class), you need the network to choose one class out of many.
That requires a probability distribution where:

Only one class should dominate

All probabilities must compete → total = 1

👉 Sigmoid fails here because it treats each class independently.

❌ Why Sigmoid is Wrong for Multi-Class Classification
Example with 3 Classes:

With sigmoid, you might get:

[0.7, 0.6, 0.8]


These do not sum to 1

The model thinks all three are likely, which makes no sense when only one class is correct

✅ Why Softmax is Correct

With softmax, you get:

[0.90, 0.05, 0.05]


✔ Clear single winner → Class 1
✔ Sum = 1 → Valid probability distribution
✔ Perfect for Categorical Cross-Entropy

🧠 Final One-Line Answer

Sigmoid treats each class independently (multi-label), while Softmax forces competition and produces a probability distribution (multi-class). That's why Softmax is used with categorical cross-entropy.



<img width="1501" height="749" alt="image" src="https://github.com/user-attachments/assets/4f6d5139-4765-4e1e-bef2-fdf47050bf34" />




Left: The full surface 
𝑧=𝑥2+𝑦2z=x2+y2 — a 3D paraboloid.

Right: A horizontal slice (level curve) at 𝑧=1. 
x2+y2=1 

This shows the key idea:

The function itself is not a circle — it's a curved 3D surface.

But any constant height slice is a circle in the 
𝑥𝑦 xy-plane. 



The formula shown in the image is correct. It represents the multivariable chain rule when a function 
ℎ depends on two inner functions f(x) and 𝑔(𝑥) both of which depend on 𝑥

<img width="657" height="119" alt="image" src="https://github.com/user-attachments/assets/d0b748d0-174f-4354-985d-42dfb625d6de" />



<img width="903" height="345" alt="image" src="https://github.com/user-attachments/assets/c971e545-111a-4432-b265-337e8fd4e213" />



Graph of Loss Function and Complicated Cost Function of (two weights and the loss) in 3D:

<img width="919" height="615" alt="image" src="https://github.com/user-attachments/assets/a4391947-7c89-46a5-8dec-8111535750d5" />
<br><br>

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0cab7bef-e4c4-4471-a89d-a4c98ffc958f" />

<br> <br>
🔹 The optimizer sees very noisy gradient updates every step. <br>
🔹 EWMA keeps a memory of the recent gradient direction — “weighted” so recent steps matter more. <br>
🔹 This helps move the parameters smoothly toward the minimum, avoiding zig-zags.

<br>

❌ EWMA does not mean “average weight updates in reaching the final solution.”
✅ It means “smoothed tracking of some quantity (like gradient or loss), which helps guide the optimizer toward the solution.”
<br>
In SGD with Momentum, this horizontal velocity component makes the GD take such steps(comparatively fewer steps than normal SGD)
<br>
Lessens zig-zag motion in vertical direction, increases movement in horizontal direction <br>

<img width="791" height="252" alt="image" src="https://github.com/user-attachments/assets/8b388fad-feae-41bf-b063-e018550d03de" />

<img width="738" height="195" alt="image" src="https://github.com/user-attachments/assets/ce9cb8b9-e64a-448b-b916-06884ef98f88" />


<br>

Problem with SGD:<br>

<img width="1438" height="936" alt="image" src="https://github.com/user-attachments/assets/eb933955-c5f7-4aeb-8216-01e98337c974" />

<a href="https://www.analyticsvidhya.com/blog/2021/06/guide-to-gradient-descent-and-its-variants-with-python-implementation/"> guide-to-gradient-descent-and-its-variants </a>

<a href="https://medium.com/@abhishekjainindore24/optimizers-part-3-sgd-with-momentum-ee21a97fe737"> sgd-with-momentum </a>
<br>

<p align="center">
  <img src="https://raw.githubusercontent.com/philoma/blogs/main/assets/training.gif" alt="Training Animation" width="600">
  <br>
  <em>Figure: Model training visualization.</em>
</p>


