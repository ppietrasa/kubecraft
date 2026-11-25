path of a packet from host2 (10.1.4.2) to host3 (10.1.5.2):

hop 1: 10.1.4.1 (srl2)
hop 2: 10.1.2.1 (srl1)
hop 3: 10.1.3.2 (srl3) (handed over to e1/2)
hop 4: 10.1.5.2

back route:

hop 1: 10.1.5.1 (srl3)
hop 2: 10.1.3.1 (srl1)
hop 3: 10.1.2.2 (srl2) (handed over to e1/2)
hop 4: 10.1.4.2

