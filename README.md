# chaos-mapping-iamge-encryption
Image encryption method using bitwise XOR combined with nonlinear mapping of chaotic systems


This work first uses bitwise XOR operations to implement image encryption and decryption processing, and then designs a graphical operation interface to allow users to use this image encryption and decryption program, and then analyzes this algorithm to select plaintext attacks and unique attacks. The security of ciphertext attacks is then analyzed, and the current research status of image encryption is analyzed. Finally, a new image encryption algorithm is proposed based on the chaotic system.


First, explain the henon map. The henon map is a two-dimensional nonlinear dynamic system defined by the following iterative equation:
x(n+1) = y(n) + 1 - a * x(n)^2
y(n+1) = b * x(n)
Among them, x(n), y(n) is the current state, x(n+1), y(n+1) is the next state, a and b are mapping parameters, which are generated through multiple rounds of iteration Complex, seemingly random chaos tables.
The solution is to design a henon_map function based on the original bitwise XOR, iteratively calculate the values ​​of x and y, and add them modulo 256 to generate a chaos table, and then use the original xor to get The encrypted image rgb matrix interacts with the chaos table (direct addition in the demonstration algorithm) to obtain the final encrypted image. The decryption process is the same.
