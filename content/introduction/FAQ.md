---
date: '2025-07-24T07:46:08+02:00'
title: 'FAQ'
math: true
---
> [!NOTE]
> Q: Will the new algorithms slow us down?

  A: No.

{{< tabs items="In a nutshell,Cryptography,TLS handshake" >}}

    {{< tab >}}
    Not to a degree that people will be able to notice.
    {{< /tab >}}

    {{< tab >}}
    It depends on the algorithm. For ML-DSA and FN-DSA, very roughly speaking:
    - Signature verification speeds will be mostly unaffected.
    - Signature generation speeds and  will be 10 times slower than EdDSA, but 10 times faster than RSA -- and still microseconds on unconstrained devices.
    - Public keys and signature will be ~10 times larger -- but still about a kilobyte instead of 100 bytes.
    See the (cloudflare blog)[https://blog.cloudflare.com/another-look-at-pq-signatures/#the-algorithms] for a quick summary and the (signature zoo)[https://pqshield.github.io/nist-sigs-zoo/#performance] for more detail.
    {{< /tab >}}
    
    {{< tab >}}

    (Chrome has been offering hybrid key exchange mechanisms since late 2023)[https://security.googleblog.com/2024/09/a-new-path-for-kyber-on-web.html] - that means running **both** the classical and the post-quantum version -- and aside from a few initial hick-ups, hardly anyone even noticed.

    Due to the larger public key and signature sizes, certificate chains will be larger. Verification times remain of a similar order of magnitude, but overall handshake times may be affected.

    (Cloudflare)[https://blog.cloudflare.com/another-look-at-pq-signatures/#how-many-added-bytes-are-too-many-for-tls] and google report a ~10 to 15% slowdown **in the handshake** protocol -- i.e., when a session is established, not in the transmission of content -- for  an extra ~1 to 10 kb of data.
    
    Some failures were observed when adding more than 9kb of data to the handshake, so long certificate chains may cause issues -- but it is not unreasonable to expect this to become an insignificant fraction with updates over the next few years.
    {{< /tab >}}
    
{{< /tabs >}}



> [!NOTE]
> Q: Are we going to need a quantum computer or new quantum hardware in our PCs and phones to use the new algorithms?

A: No.

You may need some new hardware for dedicated cryptographic processing -- smart cards, secure elements, TPMs, security keys etc. -- but this is mostly because
- the firmware is designed to not be updatable over-the-air for security reasons,
- the hardware implements specific algorithms for efficiency,
- the hardware was not designed to cope with specific requirements, such as there not being enough RAM to store the new, larger keys.

You will need to keep your software updated with the latest patches -- but you're doing that already, right?

... Right?