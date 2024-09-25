<img width="955" alt="image" src="https://github.com/user-attachments/assets/66ca6292-a8d0-40fd-8193-5279be9f2a74"># EX.-NO-2-B-IMPLEMENTATION-OF-RSA

## AIM:
  To write a C program to implement the RSA encryption algorithm.
  
## ALGORITHM:

  STEP-1: Select two co-prime numbers as p and q.
  
  STEP-2: Compute n as the product of p and q.
  
  STEP-3: Compute (p-1)*(q-1) and store it in z.
  
  STEP-4: Select a random prime number e that is less than that of z.
  
  STEP-5: Compute the private key, d as e * mod-1(z).
  
  STEP-6: The cipher text is computed as messagee *
  
  STEP-7: Decryption is done as cipherdmod n.
  
## PROGRAM: 
```
#include <stdio.h>
#include <math.h>

int gcd(int a, int h) {
int temp;
while (1) {
    temp = a % h;
    if (temp == 0) {
        return h;
    }
    a = h;
    h = temp;
}
}

int main() {
int p = 3;
int q = 7;
int n = p * q;
int e = 2;
int phi = (p - 1) * (q - 1);

while (e < phi) {
    if (gcd(e, phi) == 1) {
        break;
    } else {
        e = e + 1;
    }
}

int k = 2;
double d = (1.0 + (k * phi)) / e;

// Message to be encrypted
double msg = 12.0;

printf("Message data = %f\n", msg);

// Encryption c = (msg ^ e) % n
double c = pow(msg, e);
c = fmod(c, n);
printf("Encrypted data = %f\n", c);

// Decryption m = (c ^ d) % n
double m = pow(c, d);
m = fmod(m, n);
printf("Original Message Sent = %f\n", m);

return 0;
}
```
## OUTPUT:
<img width="955" alt="Ex 8" src="https://github.com/user-attachments/assets/c1a7c106-23e4-43fe-a986-057be18833d2">

## RESULT:
  Thus the C program to implement RSA encryption technique had been implemented successfully
