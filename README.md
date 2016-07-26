rsa-wiener-attack
=================

A Python implementation of the Wiener attack on RSA public-key encryption scheme.

It uses some results about continued fractions approximations to infer the private key from public key in the cases the encryption exponent is too small or too large.
# WeebCTF 2016 (RSA)
Problems:
N: 20977962824386032405913740351351484770365376020749771327964677874792628973475123705274027527115996059266951191525962385512144356322353007496636498810519266044243595295618754483282589445704707360849369
e: 7521929628795412779702906947281798942813700472555375539871057273372782699059766301118781185777299112863693951400599475359610255660553918613882824833946454411640962490817673964913918960613770547226759
c: 1683341545080995401311072423625275950589865037272173936304034549800161893527994639299615473186295798410491813082873705397028072324054178191589559176726355861088321636815395399015324738283185698948468
(http://play.weebctf.easyctf.com/files/rsa!!/RSA.txt)

Solve:
e ~ n => d << -> Wiener's attack
boneh_durfee.sage -> Sage with: d < N ^ (0.26) and m = 4 -> d = 4291712803058965225956504173677388635317145150515799
m = pow(c,d,n) = 191862100487585295956414894320257580235061617651119319752735101
hex(m) = 0x776565627b6170796b6872756c7774766b70686b76617765797dL
"...".decode("hex") = weeb{apykhrulwtvkphkvawey}

Similiar:
1. https://github.com/smokeleeteveryday/CTF_WRITEUPS/tree/master/2015/ASISCTF_FINALS/crypto/bodu
