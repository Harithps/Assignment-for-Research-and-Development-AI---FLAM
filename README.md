# Assignment-for-Research-and-Development-AI---FLAM
Given: 
An Excel spreadsheet (xy_dataset.csv) with x and y columns, respectively.
Parametric equation of the curve: 
<img width="546" height="170" alt="image" src="https://github.com/user-attachments/assets/7f3e1512-09ef-4a52-970f-88515dc58a72" />
with unknowns: θ, M, X, which are to be found.
where 0deg < θ < 50deg, -0.05<M<0.05, 0<X<100 and parameter t has range 6<t<60

To find: θ,M,X and L1 distance
Also, given that "uniformly sampled points" tells us that the points are evenly spread.

Solution: 
1. Generating t-values uniformly [using np.linspace(0,60,N)
2. Defining the model with the given equation of curve.
   def model(params, t):
    theta_deg, M, X, = params
    theta = np.deg2rad(theta_deg)
    x = t * np.cos(theta) - np.exp(M * np.abs(t)) * np.sin(0.3 * t) * np.sin(theta) + X
    y = 42 + t * np.sin(theta) + np.exp(M * np.abs(t)) * np.sin(0.3 * t) * np.cos(theta)
    return x, y
3. Optimizing paramters theta, M, X. I have optimized them to find the closest fit for the graph.
4. Computing Mean L1 value and plotting the graph.

Key observations : 
1. The numeric L1 value can be less if we change the t-spacing. But its given that the points are uniformly spread.
3. Sometimes L1 value can be less but the shape of the curve can be completely wrong. Which is due to overfitting and using random parameters to just reduce the value.

Output: 
The aim is to find the closest possible curve ( both visually and mathematically)
<img width="609" height="470" alt="image" src="https://github.com/user-attachments/assets/acd2344a-5b1a-4e51-a94b-7a2059112308" />
The Optimal parameters:
θ = 30.000°
M = 0.02622
X = 55.432
Mean L1 Distance: 25.29857

Google colab notebook link : https://colab.research.google.com/drive/18zWePmdQPR1T9vcRUk0_LqSkR5JDGybN?usp=sharing
