# Federated Learning in Active STARS-Aided Uplink Networks
This section conducts simulation experiments to validate the accuracy of performance analysis results in comparison with the performance of ASTARS uplink networks with FL. Additionally, the results are compared with various types of RIS. Unless stated otherwise, the simulation parameters are presented in Table II. Consider a Cartesian 3D coordinate system with the BS located at \((0,0,10)\) and the ASTARS positioned at \((50,0,10)\). The set for local devices and \(K\) are as follows: the \(N\) devices in the reflective region are evenly distributed in region \(I_1 \triangleq \{(50 + x, 50 + y, 0) : 0 \leq x \leq 20, -10 \leq y \leq 10\}\), and similarly the \(M\) devices in the refractive region are evenly distributed in \(I_2 \triangleq \{(50 + x, 50 + y, 0) : -20 \leq x \leq 0, -10 \leq y \leq 10\}\).

**TABLE II**  
SIMULATION PARAMETERS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulation repeated | 10 iterations |
| Rician factor | \(\kappa = -5\) dB |
| Amplitude coefficients of ASTARS elements | \(\beta_r = 0.7, \beta_t = 0.3\) |
| Pass loss factors | \(\alpha = 2, \eta_0 = -30\) dB |
| Amplified thermal noise | \(\sigma_e^2 = -70\) dBm |
| Noise power | \(\sigma_0 = \sigma_{re}^2 = -90\) dBm |
| Learning rate | \(\eta = 0.01\) |
| Number of users | \(N = M = 40\) |
| Regularization parameter | \(\rho = 1\) |
| Number of Reflection Units | \(Q = 30\) |
| Number of receiving antennas | \(N = 5\) |
| Amplification Factors of ASTARS | \(\lambda = 5\) |

Set 1 involves local users with identical data sizes, where \(K\) is set to 750. In set 2, local users have varying data sizes, with half of the users' datasets randomly sampled in region [100; 200] and the other half in region [1000; 2000]. Intuitively, the data from the different devices in set 1 are similar, indicating no significant discreteness issue. Conversely, in set 2, the data from various devices are heterogeneous, leading to a notable discreteness problem.

To evaluate the performance of ASTARS uplink networks integrated with FL, we conduct experiments using the MNIST dataset. Specifically, we implement a convolutional neural network (CNN) for the handwritten digit classification task. The architecture consists of two convolutional layers with a kernel size of \(5 \times 5\), each followed by a maximum pooling layer sized \(2 \times 2\). This is followed by a batch normalization layer, a fully connected layer with 50 units, a ReLU activation layer, and a softmax output layer. The loss function utilized for training is the cross‑entropy loss.

For the purpose of comparisons, we consider the following baselines in our experiments. All baselines are adjusted using the proposed SCA algorithm for \(\mathbf{f}\), \(\Theta^n\), and \(\Theta^m\):

1) **Noise‑free**: In light of the absence of communication noise throughout the communication process and the optimal reception and decoding of user messages, this scenario can be considered an ideal condition.

2) **Pstars**: In this case, the number of reflecting/transmitting elements is the same as in ASTARS. Nevertheless, due to the absence of signal amplification in PSTARS, signal attenuation may potentially result in data loss for a subset of users.

3) **Ris**: Two RISs were implemented to accommodate both reflected and transmitted signals, thereby addressing the requirements of full‑space users. However, this approach inevitably resulted in some signal loss.

4) **Without RIS**: The user signal is transmitted directly to the BS, where the severe attenuation of the signal causes the BS to experience difficulties in receiving user data.

### A. FL With Batch Gradient Descent

In Fig. 2, we plot the test accuracy of ASTARS uplink networks with FL for set 1, alongside the test accuracy for various comparison benchmarks. To prevent singular values, each curve is derived from ten Monte Carlo averages. As the data from different devices in set 1 are evenly distributed, there is no significant dispersion problem. Comparing the different types of RIS, it is evident that the ASTARS uplink networks with FL system exhibits the best performance. This illustrates the superiority of ASTARS in mitigating multiplicative fading through signal amplification. Additionally, by comparing the MM algorithm and the DC algorithm, the experiment found that both algorithms can also achieve higher test accuracy. This is due to ASTARS amplifying the uplink signal and mitigating the discreteness issue. Moreover, without the assistance of RIS, the performance of FL deteriorates. Similarly, Fig. 3 depicts the test accuracy of ASTARS uplink networks with FL for set 2. It is evident that the set 2 scenario encounters a significant discreteness issue, as reflected in the test accuracy.

In Figs. 4 and 5, we plot the test accuracy achieved with different numbers of reflection/transmission elements under the conditions of set 1 and set 2, respectively. Under the condition of set 1, various RISs configurations can attain the optimal test accuracy when \(Q = 20\); under the condition of set 2, different RISs configurations can only approach the optimal test accuracy when \(Q = 40\). ASTARS uplink networks with FL necessitates a smaller number of reflection/transmission elements to achieve optimal test accuracy compared to the findings reported in other literatures.


### B. FL With Mini‑Batch Gradient Descent

In this subsection, consider a FL framework for small‑batch gradient descent. In particularly, the training dataset is first partitioned into small batches of equal size, the gradient \(\eta_i^*\) of each small batch is computed, then these gradients are averaged \(\eta^* = \sum_{i=1}^{I}\eta_i^* / I\) at BS, and finally the above steps are repeated.

In Fig. 6, we plot the test accuracy of ASTARS uplink networks with FL under set 1 and small‑batch gradient descent. Additionally, it plots the test accuracy for different baselines. It is observed that the speed of FL convergence improves across all the different frameworks. This improvement is attributed to the fact that the FL system only needs to compute the gradient of each small batch during updating, rather than traversing the entire dataset. Calculating the gradient based on each small batch reduces the FL overhead, while the parameter updates are unaffected by singular values, resulting in higher test accuracy. Similarly, Fig. 7 illustrates the test accuracy of ASTARS uplink networks with FL under set 2 and small‑batch gradient descent. The utilization of ASTARS uplink networks with FL mitigates the discreteness issue by reducing communication errors, thereby resulting in superior test accuracy compared to all baselines.

Finally, Figs. 8 and 9 depict the test accuracy achieved with different numbers of reflection/transmission elements under the conditions of set 1 and set 2, respectively. It is observed that ASTARS uplink networks with FL can achieve the highest test accuracy. Additionally, ASTARS uplink networks requires fewer reflection units to achieve higher test accuracy under the condition of set 2.


### C. FL With Different Amplification Factors \(\lambda\)

In Fig. 10, we illustrate the impact of different ASTARS amplification factors on the learning rate to highlight the advantages of ASTARS‑assisted FL. One observation is that the learning rate of ASTARS‑assisted FL reaches its optimal value at amplification factors of 10 and 15. This is attributed to the amplification effect of ASTARS, which enhances the signal, allowing for better transmission to the BS. However, when the amplification factor is set to 5, the optimal result cannot be achieved under Simulation Condition 1, as signal loss occurs during transmission. On the other hand, when the amplification factor is too high, thermal noise becomes the dominant factor, resulting in a decline in learning accuracy. This suggests that optimizing the choice of amplification factor could be a promising direction for future research.


# STARS Assisted Semi-Grant-Free NOMA Communications

In this section, simulation results are presented to demonstrate the accuracy of the theoretical analyses for STARS‑MCS and STARS‑MCS‑SPC networks with ipSIC/pSIC. The simulation parameters used, unless otherwise specified, are illustrated in Table I, where BPCU is the short for bit per channel use. To ensure the accuracy of approximate expressions, the complexity‑accuracy trade‑off parameters are set to 300. The noise power is \(\sigma_0^2 = -173 + 10\log (BW)\) dBm, where the bandwidth \(BW = 100\) MHz. The path loss at reference distance 1 meter is set to \(\beta_0 = -30\) dB. We set the GBU and GFUs have the same transmit power, i.e., \(P_f = P_b\), which is more relevant to practical applications [9]. To demonstrate the performance enhancement of the proposed STARS‑MCS‑SPC scheme, the STARS‑MCS and STARS‑dynamic scheme [19] are selected as the benchmark protocols. In particular, the admitted GFUs in STARS‑dynamic scheme is randomly selected from all GFUs with a fixed decoding order. Moreover, to present the benefits of introducing STARS into the SGF networks, we compare the performance of RIS‑MCS in terms of outage probability. In RIS‑MCS networks, to obtain \(360^\circ\) coverage, we employ a surface made up of one transmit‑only RIS and one reflect‑only RIS [28].

**TABLE I**  
SIMULATION PARAMETERS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^6\) iterations |
| Rician factor | \(\kappa = -7\) dB |
| Number of GFUs | \(M = 3\) |
| Path loss expression | \(\alpha = 2\) |
| ipSIC interference level | \(\Delta = -30\) dB |
| Number of STARS elements | \(L = 10\) |
| Distance from STARS to BS | \(d_s = 50\) m |
| Coverage radius of STARS | \(R = 50\) m |
| Target data rates for GBU and GFU | \(\hat{R}_b = 1.2\) BPCU, \(\hat{R}_f = 1.2\) BPCU |
| Amplitude coefficients of configurable elements | \(\beta_t = 0.5\), \(\beta_r = 0.5\) |

### A. Compare With Different Protocols

![Figure 2: Compare with different protocols](图片占位符_Fig2)

Fig. 2(a) plots the system outage probability of STARS‑MCS‑SPC and benchmarks versus transmit power \(P_f\) with \(\hat{\gamma}_f\hat{\gamma}_b \leq 1\). The results of STARS‑MCS and STARS‑MCS‑SPC are obtained based on (22) and (23). It can be observed that the outage probability curves given by Monte Carlo simulations are in perfect match with the theoretical analytical expressions. One can observe that the outage performance of both STARS‑MCS and STARS‑MCS‑SPC outperforms the networks of STARS‑dynamic at the condition of pSIC. This is due to the fact that the MCS protocol has a more flexible decoding strategy, which can effectively reduce the interference between GFU and GBU. Another reason is that the MCS protocol can select the GFU with maximum channel distribution function value to access the GBU's resource blocks. This filtering mechanism provides an enhanced diversity gain for the networks, which is consistent with the insights in Remark 1 and Remark 3. Another phenomenon is that, under the pSIC condition, the outage performance of STARS‑MCS‑SPC surpasses that of STARS‑MCS. This is attributed to the SPC strategy, which ensures that the signals of GBU and GFU can be decoded under the optimal order by restricting the adjustment of transmit power and the reflection/transmission coefficients of STARS. Moreover, from this figure, we can observe that under the conditions of ipSIC, the networks employing three different strategies all experience outage probability error floors. The residual interference generated by ipSIC is the direct cause of this phenomenon, which shows a destructive impact on the performance of the SGF networks. Therefore, understanding the impact of ipSIC on SGF networks and devising methods to eliminate it are crucial considerations for future research.

Fig. 2(b) illustrates the outage probability in \(P_f\) with \(\hat{\gamma}_f\hat{\gamma}_b > 1\). The main variation is that even with the pSIC mechanism, STARS‑MCS still experiences an outage probability error floor in high SNR regions. This suggests that the strategy without power control cannot achieve further performance gains in the high SNR regions. The error floor of STARS‑MCS is mainly caused by \(\Lambda_b \leq H_b \leq \infty\) in \(J_2\). Whereas, with the introduction of the SPC, an additional restriction \(\Lambda_b \leq H_b \leq \Lambda_1\) is placed on \(H_b\). This restriction causes the outage probability to keep decreasing as transmit power increases, thus eliminating the error floor. Furthermore, we assume the system operates in either grant‑free or grant‑based transmission modes for non‑NOMA scenarios. In the grant‑based scenario, each user exclusively occupies a resource block for OMA transmission, but the number of users that can be accommodated is limited. It can be observed that the outage probabilities of STARS‑MCS‑SPC‑pSIC and STARS‑grant‑based are relatively close. This is because the proposed MCS scheme is capable of selecting the optimal GFU to access the resource blocks of GBU. On the other hand, the STARS‑grant‑free scheme exhibits the worst performance due to allowing a large number of GFUs to flood the system, resulting in severe interference. Therefore, the SGF‑NOMA scheme can be considered the trade‑off between the QoS and the number of user accesses.

![Figure 3: The system throughput versus transmit power](图片占位符_Fig3)

Fig. 3 compares the system throughput of STARS‑MCS‑SPC with benchmarks in delay‑limited transmission mode. From the figure we can observe that the system throughput of STARS‑MCS‑SPC is better than the other two benchmarks. Moreover, all schemes except STARS‑MCS‑SPC with pSIC cannot achieve the theoretical upper limit of throughput in delay‑limited transmission mode. This is attributable to the fact that the system throughput, in the delay‑limiting transmission mode, is directly determined by the outage probability. The interference caused by ipSIC and the deficiencies of the STARS‑MCS scheme both result in the system throughput falling short of the theoretical maximum.

![Figure 4: The outage probability versus transmit power with different \(L\) and \(M\)](图片占位符_Fig4)

Fig. 4 plots outage probability of STARS‑MCS‑SPC with pSIC under various \(L\) and \(M\). The results of \(U_f\) and \(U_b\) with pSIC are obtained based on (18) and (21), respectively. The corresponding asymptotic outage probabilities are obtained according to (32) and (34). A noteworthy trend is the steepening of \(U_f\)'s outage probability curves with the increase in the number of GFUs. This indicates that the proposed STARS‑MCS‑SPC network gives a favourable performance in multi‑user scenarios. One can also observe that the \(U_b\)'s outage probability decays more rapidly as \(L\) increases. The main reason is that the diversity order of \(U_b\) with pSIC is proportional to \(L\), which is consistent with the conclusions in Remark 6.

### B. Compare With RIS‑MCS

![Figure 5: Compare with the RIS‑MCS network](图片占位符_Fig5)

In Fig. 5(a), we study the outage probability STARS‑MCS‑SPC with ipSIC versus the transmission coefficients \(\beta_t\). One can be observed from Fig. 5(a) that the outage probability of STARS‑MCS‑SPC first decreases and then increases as \(\beta_t\) becomes larger. The reason for the lower outage probability is that the increase of \(\beta_t\) can directly improve the receiving SNR of \(U_b\) at BS. However, as \(\beta_t\) increases, \(\beta_r\) decreases; which will lead to an increase in the outage probability of \(U_f\). Eventually, the outage probability of \(U_f\) dominates (23), which will cause the system outage probability to change from a decreasing trend to an increasing trend. By adjusting amplitude coefficients of transmission elements, the better outage performance can be obtained for STARS‑MCS‑SPC compared to RIS‑MCS. This can be explained by the fact that STARS offers new degrees of freedom for signals propagation to enhance the performance of SGF transmission. However, the performance of STARS‑MCS‑SPC is not always superior to that of RIS‑MCS, for example, \(\beta_t = 0.1\). Moreover, one interesting observation is that the optimal \(\beta_t\) for minimizing outage probability varies at different target rates. Therefore, finding the optimal transmission and reflection coefficients at different target rates is the key to achieving enhanced outage performance for STARS‑MCS‑SPC.

Fig. 5(b) plots the system outage probability STARS‑MCS‑SPC and RIS‑MCS versus the number of elements \(L\) with \(P_f = 30\) dBm. It can be observed that as the number of elements increases, both outage probability of STARS‑MCS‑SPC with ipSIC and pSIC decrease. This is because a greater number of STARS elements can effectively enhance the quality of the communication channel, thereby achieving higher diversity gains. However, compared to RIS, STARS can simultaneously transmit and reflect signals to provide more path options and higher signal diversity. Therefore, deploying STARS in SGF‑NOMA networks can yield more significant performance gains from an increased number of elements.

### C. Compare With Different Parameters

![Figure 6: Compare with different parameters](图片占位符_Fig6)

Fig. 6(a), we present the outage probability of STARS‑MCS‑SPC with ipSIC/pSIC versus the STARS deployment location. Specifically, we assume that the sum of the distance \(d_s\) from STARS to BS and the service radius \(R\) is fixed as \(100\) m, i.e., \(d_s + R = 100\) m, and STARS move between the users and BS. From the figure we can see that the outage probability is lower when STARS is deployed at near‑BS and near‑user. The outage performance is worst when STARS is deployed in the middle of the BS and user. This is attributed to the fact that the multiplicative fading is strongest when STARS is in the middle. Moreover, the path loss exponent is mainly determined by the communication environments. Different \(\alpha\) should be used for different communication environments, where \(\alpha = 2\) indicates free space and \(\alpha = [2.3, 2.6]\) indicates urban cellular networks. One can observe that as \(\alpha\) decreases, the outage performance is improved, which is due to the reduced influence of path loss on the transmitted signal.

Fig. 6(b) plots outage probability of STARS‑MCS‑SPC with ipSIC under various residual interference factor \(\Delta\). We can observe that both GFU and GBU in STARS‑MCS‑SPC experience error floor in ipSIC conditions. By reducing the ipSIC residual interference factor \(\Delta\), the outage performance of user decoded messages can be effectively improved.

---



# Secrecy Performance Analysis of Multi-Functional RIS-Assisted NOMA Networks

In this section, numerical results are provided to verify the accuracy of the theoretical expressions derived in Section IV. Distinct secrecy insights of MF‑RIS‑assisted NOMA networks are also discussed in detail. Without otherwise stated, we set \(\alpha = 2.2\), \(\chi = -30\) dB [38]. The distance parameters are set to be \(R_d = 20\) m, \(d_b = 200\) m, and \(d_e = 15\) m. The amplification factors at MF‑RIS are \(\beta_r = \beta_t = 10\) dB. Supposing that residual interference is approximately equivalent to \(10\%\) of the power of the decoded signal, the imperfect SIC parameter in external and internal wiretapping scenarios can be set as \(\Omega_r^{ip} \approx -126.13\) dB, \(\Omega_{e,r}^{ip} \approx -130.26\) dB, \(\Omega_t^{ip} \approx -125.04\) dB and \(\Omega_{r,t}^{ip} \approx -129.17\) dB, respectively [38]. The power setup of AWGN and thermal noise are given as \(\sigma_n^2 = \sigma_e^2 = -90\) dBm and \(\sigma_s^2 = -80\) dBm, respectively [39], [41]. In addition, the target secrecy rates for users \(R_r = 0.1\) and \(R_t = 0.05\) bit per channel use (BPCU) [48]. The power consumed by phase shifters and direct current biasing circuits are \(P_{ps} = -10\) and \(P_{dc} = -5\) dBm [50], respectively. To highlight the secrecy performance of the proposed network, the active RIS and STAR‑RIS are both considered as benchmarks, which are defined as follows.

1) **Active RIS**: Active RIS allows \(M/2\) reconfigurable elements to perform only reflection functions, while the other \(M/2\) elements exclusively perform refraction functions, and all the elements can independently implement phase modulation. Additionally, active RIS has signal amplification capabilities and each reconfigurable element is equipped with a set of reflection or refraction power amplifiers. We suppose that the elements have identical amplification factors, i.e., \(\beta_{t,m} = \beta_{r,m}\), \(\beta_{\phi,1} = \beta_{\phi,2} = \dots = \beta_{\phi,M/2}\) and \(\phi \in \{t,r\}\).

2) **STAR‑RIS**: STAR‑RIS can also perform dual‑sided signal transmission, based on an ES strategy, simultaneously radiating the modulated signals to both the reflection and refraction regions. Unlike MF‑RIS, STAR‑RIS lacks signal amplification capabilities and does not include any active devices related to power amplification. In other words, STAR‑RIS is almost passive. To be fair, the ES coefficient for STAR‑RIS is set to be the same as that for MF‑RIS, i.e., \(e_r = 0.8\) and \(e_t = 0.2\).

### A. External Wiretapping Scenario

![Figure 2: The SOP performance versus the total power budget in the external wiretapping scenario, where \(M = 12\), \(e_r = 0.8\), \(e_t = 0.2\), \(a_r = 0.25\) and \(a_t = 0.75\).](图片占位符_Fig2)

Fig. 2 plots the SOP performance versus the system power budget in the external eavesdropping scenario. It is clear to see that the obtained analytical expressions are consistent with simulation results during the entire range of power budget, which validates the accuracy of analytical methods applied. Within the high SNR region, trends of the theoretical lines gradually converge with the asymptotic ones based on (26), (27) and (28) manifesting the validity of asymptotic theoretical expressions. Since the slopes of the asymptotic lines for MF‑RIS and STAR‑RIS are both greater than that of the active RIS, this phenomenon also corroborates the analysis in Remark 1. From Fig. 2, we can observe that under the same system power constraints, the SOP performance of the proposed MF‑RIS scheme significantly outperforms the STAR‑RIS and active RIS alternatives. This is primarily due to the inherent advantages of MF‑RIS, which encompass full‑space coverage and signal amplification capabilities, capable of mitigating the adverse effects of multiplicative fading while enabling 360‑degree wireless transmission. Additionally, Fig. 2 illustrates the impact of imperfect SIC on the physical layer secrecy for \(u_r\). For active RIS, STAR‑RIS and MF‑RIS, the residual interference generated by imperfect SIC forces the SOP curves for \(u_r\) to converge to different error floors. This indicates that in the high SNR region, residual interference poses a more severe threat to users' privacy than thermal noise.

![Figure 3: The SOP performance versus the number of reconfigurable elements in the external eavesdropping scenario.](图片占位符_Fig3)

Fig. 3 plots the SOP performance versus the number of reconfigurable elements in the external eavesdropping scenario. Similar to Fig. 2, the numerical results align closely with the theoretical expressions. On the one hand, it can be observed that increasing the number of elements is advantageous in reducing the SOP for users in both the reflection and refraction regions. On the other hand, owing to MF‑RIS's capability for independent bidirectional signal manipulation and amplification, it can achieve equivalent secrecy performance with the fewest reconfigurable elements compared to active RIS and STAR‑RIS. Furthermore, we can note that the presence of imperfect SIC diminishes the performance gains obtained from MF‑RIS elements. Therefore, devising appropriate SIC receivers to mitigate the impact of residual interference is crucial for enhancing the physical layer secrecy of MF‑RIS‑assisted NOMA networks.

![Figure 4: The SOP performance versus the total power budget and ES coefficients in the external wiretapping scenario, where \(M = 12\), \(a_r = 0.25\) and \(a_t = 0.75\).](图片占位符_Fig4)

Fig. 4 plots the system SOP performance versus the total power budget and the ES parameter in the external eavesdropping scenario. As the system power budget increases, the performance of the MF‑RIS‑assisted NOMA networks under perfect SIC improves steadily in terms of SOP. However, in the imperfect SIC case, the system SOP gradually converging to an error floor since the residual interference escalates with higher power budget. Furthermore, it is evident that when MF‑RIS allocates more power to \(u_r\) (i.e., \(e_r > 0.5\)), the system secrecy outage behavior becomes better. However, when the \(e_r\) exceeds a certain threshold, the system's SOP increases instead of decreasing. This is because that an excessively large \(e_r\) leads to a reduction in the energy allocated to \(u_t\), consequently diminishing the SINR when \(u_t\) decoding its own signal, ultimately compromising its secrecy capacity. This underscores the critical importance of selecting an appropriate ES strategy at the MF‑RIS to safeguard NOMA networks.

![Figure 5: The secrecy throughput performance versus the total power budget in the external wiretapping scenario, where \(M = 12\), \(e_r = 0.8\), \(e_t = 0.2\), \(a_r = 0.25\) and \(a_t = 0.75\).](图片占位符_Fig5)

Fig. 5 plots the system secrecy throughput versus the total power budget in the external eavesdropping scenario. From the figure, it can be observed that the delay‑limited secrecy throughput of the MF‑RIS is consistently higher than those of the benchmarks and eventually tends to stabilize with the increasing total power budget under perfect SIC case. This is because the SOP for users in the NOMA network has already become sufficiently small within high power budget. The residual interference caused by imperfect SIC has the least impact on the proposed MF‑RIS scheme, with a throughput loss of approximately 0.41 dB. In contrast, active RIS and STAR‑RIS are more significantly affected by imperfect SIC, with throughput losses of up to 1.47 dB and 1.66 dB, respectively. This indicates that the MF‑RIS demonstrates excellent robustness compared to the other two RIS configuration schemes.

![Figure 6: The secrecy throughput performance versus the residential interference and thermal noise in the external wiretapping scenario, where \(M = 12\), \(e_r = 0.8\), \(e_t = 0.25\) and \(a_t = 0.75\).](图片占位符_Fig6)

Fig. 6 plots the system secrecy throughput versus the residential interference and thermal noise in the external eavesdropping scenario. This figure illustrates that increasing the total power budget can indeed enhance the overall secrecy throughput. When the total power budget is relatively abundant (40 dBm), the secrecy throughput of the MF‑RIS‑assisted NOMA networks is primarily influenced by the residual interference as the degree of imperfect SIC is directly proportional to the transmitting power of the BS. On the contrary, when the total power budget decreases (30 dBm), the secrecy throughput is jointly determined by the residual interference as well as the thermal noise. The phenomenon illustrated in Fig. 6 also answers the first and second questions that we raised in the introduction part, indicating that further optimization of SIC performance is crucial for maximizing secrecy in high‑power regimes. These insights suggest that the design of MF‑RIS‑secured NOMA networks should carefully balance power allocation and SIC performance to enhance secrecy.

### B. Internal Wiretapping Scenario

![Figure 7: The SOP performance versus the total power budget in the internal wiretapping scenario, where \(M = 12\), \(e_r = 0.2\), \(e_t = 0.8\), \(a_r = 0.9\) and \(a_t = 0.1\).](图片占位符_Fig7)

Fig. 7 plots the SOP performance versus the total power budget in the internal eavesdropping scenario. From the figure, we can observe that the secrecy outage behavior for \(u_t\) in MF‑RIS‑assisted NOMA networks is superior to the other two benchmarks in both imperfect and perfect SIC cases. Furthermore, unlike the external eavesdropping scenario, the SOP for \(u_t\) eventually converges instead of continuing to decrease under perfect SIC conditions, and this phenomenon also corroborates the analyses in Remark 2. This is because the I‑Eve's received SNR is proportional to the transmit power of BS. Therefore, as the total power budget increases, the wiretapping capability of the I‑Eve also improves. Moreover, it can be seen that under the imperfect SIC condition, the SOP for \(u_t\) initially decreases and then increases. This can be explained by the fact that in the high SNR region, the residual interference introduced by imperfect SIC is higher. At this point, the impact of residual interference on legitimate \(u_t\) is greater compared to its impact on I‑Eve, leading to fluctuations in the SOP curve.

![Figure 8: The SOP performance versus the number of reconfigurable elements in the internal wiretapping scenario, where \(e_r = 0.2\), \(e_t = 0.8\), \(a_r = 0.9\) and \(a_t = 0.1\).](图片占位符_Fig8)

Fig. 8 plots the SOP performance versus the number of reconfigurable elements in the internal eavesdropping scenario. With the number of elements increases, the SOP of \(u_t\) gradually decreases, and the rate of decrease slows down. This is because, with a greater number of reconfigurable elements, the quality of cascaded eavesdropping channels for the I‑Eve strengthens. In other words, both \(u_t\) and I‑Eve can benefit from the beamforming gains from MF‑RIS, which is evidently different from the external eavesdropping scenario illustrated in Fig. 3. Additionally, the figure indicates that MF‑RIS achieves the same level of secrecy performance as active RIS and STAR‑RIS with only a small number of elements. This is attributed to the high diversity order and dual‑sided signal amplification capability of MF‑RIS. The SOP performances shown in Fig. 7 and Fig. 8 are remarkably different from that in the external wiretapping scenario, which also answers the last question proposed in the introduction part.

![Figure 9: The secrecy throughput performance versus the total power budget in the internal wiretapping scenario, where \(a_r = 0.9\), \(a_t = 0.1\) and \(R_t = 0.1\) BPCU.](图片占位符_Fig9)

Fig. 9 plots the secrecy throughput versus the total power budget in the internal eavesdropping scenario. It can be seen from the figure that the secrecy throughput of \(u_t\) in the MF‑RIS‑assisted NOMA networks surpasses that of the other two benchmarks, mirroring the user's secrecy throughput performance in the external eavesdropping scenario, as illustrated in Fig. 5. It is noteworthy that the method to enhance the communication secrecy for the \(u_t\) involves deferring the decoding order of confidential information until it is the last one. Furthermore, MF‑RIS should split more energy to \(u_t\), specifically with \(e_r = 0.2\) and \(e_t = 0.8\). This ES strategy aims to diminish the SINR when the I‑Eve decodes the confidential information, thereby augmenting the secrecy capacity of \(u_t\). In cases where such assurance is unattainable, i.e., with \(e_r = 0.8\) and \(e_t = 0.2\) as evidenced in the figure, the secrecy throughput of \(u_t\) in the internal eavesdropping scenario experiences a notable degradation.

---



# Relay-Satellite-Assisted LEO Constellation NOMA Communication System

### A. Simulation Parameter and Benchmarks

This section provides the numerical results to evaluate the performance of the proposed algorithms in the R‑NOMA‑BF system. The course of simulation still holds the same objective as \(\sum_{k\in \mathcal{K}, i\in \mathcal{N}}(R_i - D_i)^2\) in \(\mathcal{P}_0\) unification. Numerical verification results exceed 1000, where per user traffic demand is randomly distributed with each simulation. To evaluate the proposed algorithm effect in a realistic level, the longitude range and latitude range of the LEO constellation campaign are \([100^\circ E, 105^\circ E]\) and \([-1.5^\circ S, 1.5^\circ N]\) respectively. Actually, the six LEO satellites were randomly separated in three orbits over the region, where various geographic environments, i.e., oceans, rivers, and plains, are included [25]. Hence, the complex geography caused by uneven ground‑station deployment and user‑traffic demand, which is considered more typical for the R‑NOMA‑BF system. The relay satellite is positioned near the equator at \(103^\circ E\). The simulated users are configured as a small number of satellite‑enabled mobile terminals mounted on cars, boats, and drones [42]. Satellites related parameters and cooperative connections are referred to 3GPP TR 38.811 and TR 38.821 [43], [44]. The parameter definitions are summarized in Table I unless stated otherwise.

**TABLE I**  
SIMULATION PARAMETERS

| Parameter | Value |
|-----------|-------|
| Frequency, \(f_c\) | 11.7 GHz |
| Bandwidth, \(B_{mt_k}\) | 500 MHz |
| Satellite covers the ground longitude range | \([100^\circ E, 105^\circ E]\) |
| Satellite covers the ground Latitude range | \([-1.5^\circ S, 1.5^\circ N]\) |
| LEO satellites travel speed | 7.9 km/s |
| LEO satellites altitude | 1200 km |
| Relay satellite location | \(103^\circ E\) |
| Relay satellite altitude | 36 000 km |
| Number of LEO satellites, \(M\) | 6 |
| User receive antenna gain, \(G_r\) | 35.7 dBi |
| LEO satellite maximum transmit antenna gain, \(G_{\max}\) | 64.9 dBi |
| Number of beamforming antennas, \(L\) | 8 |
| Number of cells, \(K\) | 64 |
| Number of users per cell, \(N\) | 4 |
| Noise power, \(\sigma^2\) | \(-136\) dBW |
| Power budget per LEO satellite, \(P_s\) | 25 dBW |
| Antennas array distance | 0.5 m |
| Minimum capacity, \(R_{\min}\) | 5 Mbps |
| Traffic demand, \(D_t\) | 300 Mbps to 1300 Mbps |

We verify the excellence of the proposed algorithms by selecting several different comparison benchmarks as follows.

1) **A‑mNOMA‑BF**: Based on the scheme presented in Sections IV and V, the A‑mNOMA‑BF algorithm is reintegrated. More specifically, the modified ant colony algorithm is combined with the monotone planning algorithm of NOMA. The BF vector utilizes the SVD algorithm. The optimized variables are iterated over each other until convergence.

2) **D‑eNOMA‑BF**: Similar to the A‑mNOMA‑BF algorithm, the D‑eNOMA‑BF algorithm was redesigned as a new benchmark. The optimization results of the BF vector are obtained first. The relay satellite measures the Doppler shift with the LEO satellites and passes the threshold constraints. The power obtained by exponential planning and the obtained LEO satellite‑cell matching factor are jointly optimized. The three variables are iterated to produce the final users' satisfaction.

3) **Orthogonal Multiple Access BF (OMA‑BF)**: Since each beam includes only a user, OMA‑BF can be defined as a single‑beam problem. The BF is still optimized according to the algorithm designed in (9).

4) **Relay Satellite Nonorthogonal Multiple Access 2 Color (R‑NOMA‑2c)**: The subset of channels using the same polarization is called a color. The scheme refers to the consideration of orthogonal polarizations, i.e., right‑handed or left‑handed circular polarizations. The polarization multiplexing is considered in the existing LEO satellite‑cell and NOMA algorithms without BF vector, which includes D‑eNOMA‑2c, A‑eNOMA‑2c, D‑mNOMA‑2c, and A‑mNOMA‑2c. The power is distributed within the same polarization type [45].

5) **Relay Satellite Nonorthogonal Multiple Access 4 Color (R‑NOMA‑4c)**: Adding frequency multiplexing based on the R‑NOMA‑2c, associated algorithms contains four subbands consisting of different polarizations and frequencies, that is, D‑eNOMA‑4c, A‑eNOMA‑4c, D‑mNOMA‑4c, and A‑mNOMA‑4c. Obviously, half of the bandwidth exists reduced in these cases.

6) **Relay Satellite Nonorthogonal Multiple Access single Beam (R‑NOMA‑S)**: A single beam gets to be designed into a system, where all the antennas form a spot beam covering all users. Similarly this comparison baseline involves D‑eNOMA‑S, A‑eNOMA‑S, D‑mNOMA‑S, and A‑mNOMA‑S [46].

For testing multiple objective functions on optimization results, we applied to discuss on the basis of four existing algorithms the following two schemes.

1) **Scheme 1**: The objective function retains the second‑order difference function from \(\mathcal{P}_0\).

2) **Scheme 2**: The ratio between maximum reachable capacity and user demand is formulated in the R‑NOMA‑BF system, while limiting achievable capacity does not exceed traffic requirements, i.e., \(\max \sum_{k \in \mathcal{K}, i \in \mathcal{N}_D} \frac{R_i}{D_i}\), s.t. \(R_i \leq D_i\) [25].

### B. Performance Analysis

![Figure 2: Objective gap versus average demand traffic with various comparative algorithms in the R‑NOMA‑BF system.](图片占位符_Fig2)

Fig. 2 plots the objective gap versus average demand traffic with various comparative algorithms for OMA‑BF, A‑mNOMA‑BF, D‑mNOMA‑BF, A‑eNOMA‑BF, and D‑eNOMA‑BF. All four different algorithms have excellent control within the user demand of 500 Mbps. However, these algorithms expose significant disparities beyond 600 Mbps. As can be observed that eNOMA provides a more robust fit compared to mNOMA. In the case of demand growth from 700 to 1300 Mbps, A‑eNOMA‑BF and D‑eNOMA‑BF algorithms only dropped by 14.12% and 14.90%, respectively. The improved ant colony‑based algorithm better achieves global planning based on the optimization results calculated from a large number of pheromone. However, the Doppler‑shift algorithm only focuses on the optimal matching results for each LEO satellite, which leads to some differences between two types of algorithms in fitting ability. Since two algorithms just illustrated are excellent, the ant colony algorithm still improves matching performance, which is more valuable. Compared with that, A‑mNOMA‑BF and D‑mNOMA‑BF algorithms have a cliff‑like decline in fitting gaps, but the revised ant colony algorithm has an ameliorative role. This phenomenon indicates that the approximation of \(\mathcal{P}_1'\) in the solution process leads to loss of substantial accessible capacity.

![Figure 3: User ID versus achievable capacity for Doppler frequency shift LEO satellite‑cell assignment strategy.](图片占位符_Fig3)

Fig. 3 plots the user ID versus achievable capacity with the D‑eNOMA‑BF and D‑mNOMA‑BF algorithms. The blue and green bars represent the achievable capacity of the D‑eNOMA‑BF and D‑mNOMA‑BF algorithms, respectively. The orange curve is the users' traffic request. One observation is that the D‑eNOMA‑BF algorithm essentially allows the two types of results to overlap. In contrast, nearly \(30\%\) users differed significantly in the D‑mNOMA‑BF algorithm, where user 14 has the largest disparity of 337.37 Mbps. This phenomenon shows that the D‑eNOMA‑BF algorithm still fully achieves optimal user satisfaction at nearly 700‑Mbps user demand. We conclude that the exponential cone programming provides better user satisfaction for independent individual users. In the D‑mNOMA‑BF algorithm, the approximation accuracy of the optimization function becomes lower for too large an auxiliary variable \(\beta\) about \(p_{\max,i}\) based on (17a). The objective function is actively split and approximated into two logarithmic functions according to (13) and (14), which can narrow the desirable range of \(p_i\). As a result, D‑mNOMA‑BF algorithm has some traffic misfit for the requirement of high traffic.

![Figure 4: User ID versus achievable capacity for the A‑eNOMA‑BF and A‑mNOMA‑BF algorithms.](图片占位符_Fig4)

Furthermore, Fig. 4 plots the user ID versus achievable capacity for the A‑eNOMA‑BF and A‑mNOMA‑BF algorithms. The blue bar and red bar indicate the achievable capacity of the users in the A‑eNOMA‑BF and A‑mNOMA‑BF algorithms, respectively. The yellow curve represents the request traffic of users. It is worth mentioning that about \(30\%\) users have not achieved their satisfaction in the A‑mNOMA‑BF algorithm. The maximum distance between user 12 and its traffic demand is 275.51 Mbps. Similar with the principle of the Doppler‑shift‑based algorithm, the performance of the A‑mNOMA‑BF algorithm is still weaker than that of A‑eNOMA‑BF. It is worth noting that the improved ant colony algorithm for the LEO satellite matching cell indexing method is different from the Doppler‑shift‑based algorithm, which causes user request traffic differentiation. The average gap of users for the A‑mNOMA‑BF and D‑mNOMA‑BF algorithms are 208.12 and 301.14 Mbps, respectively. The A‑mNOMA‑BF algorithm outperforms the D‑mNOMA‑BF algorithm by 0.45 dB. Over the critical 600 to 900‑Mbps range, the eNOMA‑based algorithms are largely fitted for capacity and request traffic.

![Figure 5: Simulation results for user satisfaction and satellite transmission power. (a) Satisfaction of users versus average demand traffic with different power in R‑NOMA‑BF system. (b) Satisfaction of users versus satellite transmission power with 900 Mbps of average user demand.](图片占位符_Fig5)

Fig. 5(a) plots the traffic gap related to user demand with multiple power in the R‑NOMA‑BF system, where \(P_s = 25\) or 28 dBW. We can observe that single satellite power more higher the overall solution of user satisfaction is enhanced under power constraints. With the increasing of \(P_s\) increasing, the A‑eNOMA‑BF and D‑eNOMA‑BF algorithms are simultaneously improved by 3 dB in matching gap at 900 Mbps. The fitting ability of both the A‑mNOMA‑BF and D‑mNOMA‑BF algorithms are also boosted by 2.67 dB with power. This suggests that not only the power allocation per NOMA users is essential but also optimization in the directional power to the BF vector affects users capacity. Therefore, NOMA and BF vector power assignments make sense to be studied on the basis of payload limitations for LEO satellite cooperative communication. As a further advance, Fig. 5(b) plots the curve of user satisfaction with respect to the satellite transmission power \(P_s\), where the average user demand is 900 Mbps. As can be observed that user satisfaction is not proportional to the increase in transmit power. The formulated objective scheme concentrates on satisfying the accomplishable user demand for lower \(P_s\), which makes the relative majority of users to be assigned less power allocation. As a result, users with higher satisfaction are subjected to fewer interferences, where boosting the transmit power leads to larger gains. With the higher transmit power, user demand is basically satisfied, and this further increase in \(P_s\) will not enhance the performance much.

![Figure 6: Comparison of user satisfaction gap versus average demand traffic for multiple polarization modes.](图片占位符_Fig6)

To evaluate the impact of the BF vector and antenna polarization on the R‑NOMA‑BF system performance, Fig. 6 compares the gap among multiple polarization modes of user satisfaction versus average traffic demand. BF weights and synthesizes the signals received from multiple antenna array elements in all directions. BF is capable of focusing on a specific direction and mitigate interference for surrounding users. However, polarization multiplexing is the forward and backward of the phase angles between the electric and magnetic field components to define left‑ and right‑handed polarization. The users of different polarization types have hardly any interference with each other. For the sake of convenience, it is emphasized that main algorithms refer to 1‑color multiplexing, i.e., users occupy the entire frequency band. As can be observed, the optimal user requested traffic for 4‑color multiplexing lies only around 130 Mbps, while 2‑color multiplexing approach lies around 230 Mbps at the most appropriate user satisfaction. It illustrates that 4‑color multiplexing sacrifices bandwidth to save interuser interference and hardly has a nice answer. The correlation algorithms with the BF vector do not waste bandwidth despite controlling the interference, which highlights its performance. Furthermore, the optimization without the BF vector causes little division across the four algorithms based on polarization modes. Such a phenomenon shows that the power derived from mNOMA and eNOMA approximation no longer has negative consequences on \(p_i\) of the BF vector by (9). In Table II, we further summarize the proposed schemes for jumping out of the optimal satisfaction bound capacity. Due to 4‑color multiplexing sharing the frequency resources, these algorithms reduce achievable rates. Compared to BF‑based algorithms, 2‑color multiplexing only isolates users' interference of different polarization types, which still adversely affects traffic fitting. However, the BF‑based algorithms improve users' satisfaction by isolating interference in all directions. The total actual capacity of users represents the limit of traffic without spilling over. It is concluded that the BF‑based algorithms effectively enhance the upper bound of users' satisfaction.

**TABLE II**  
TOTAL ACTUAL USERS CAPACITY AND UNSATISFIED USERS TRAFFIC GAP OF ALGORITHMS WITH VARIOUS POLARIZATION MODES

| Algorithm | Total actual users capacity (Mbps) | Total unsatisfied users traffic gap (Mbps) |
|-----------|-----------------------------------|---------------------------------------------|
| D‑eNOMA‑4c | 50 334 | 16 982 |
| A‑eNOMA‑4c | 52 981 | 14 221 |
| D‑mNOMA‑4c | 54 018 | 13 196 |
| A‑mNOMA‑4c | 56 167 | 11 049 |
| D‑eNOMA‑2c | 94 711 | 10 984 |
| A‑eNOMA‑2c | 96 330 | 9 279 |
| D‑mNOMA‑2c | 99 837 | 5 771 |
| A‑mNOMA‑2c | 100 775 | 4 832 |
| D‑mNOMA‑BF | 174 011 | 8 390 |
| A‑mNOMA‑BF | 175 472 | 6 928 |
| D‑eNOMA‑BF | 175 629 | 6 771 |
| A‑eNOMA‑BF | 176 813 | 5 587 |

![Figure 7: Satisfaction objective value versus user demand traffic with single beam benchmarks.](图片占位符_Fig7)

Fig. 7 plots the users' satisfaction of the proposed algorithms for comparing the conventional single‑beam multiantenna scenarios. The firm and dotted lines indicate four algorithms already available above and the single‑beam comparison baselines, respectively. It shows that eNOMA‑S has inferior performance than mNOMA‑S, where the former needs to be close at \(300\) Mbps before completing users demand, whereas the latter takes \(500\) Mbps. This is because the isolated interference based on different directional power is weakened by the BF vector optimization in the multiantenna single beam. The strong power distribution characteristics of eNOMA cannot be reflected as a result. Another observation is that mNOMA grows more steeply after leaving the optimal satisfaction. This is due to the fact that auxiliary variables about \(p_i\) are no longer within the constraints by (20). Due to the limited space resources available for satellite communications, the scenarios of a single beam serving multiple users are often seen in the same direction. The R‑NOMA‑S system is a special case of the R‑NOMA‑BF system. R‑NOMA‑S systems have more focused radiant energy, while R‑NOMA‑BF systems are more concerned with suppressing interference to improve performance. This means that the interbeam interference neglect of the BF vector in exponential planning has a greater impact on eNOMA algorithms. Therefore, mNOMA is a better choice in multiantenna single beam scenarios.

![Figure 8: Performance of gap versus user demand traffic for different objective function schemes.](图片占位符_Fig8)

Fig. 8 plots the performance of gap versus user demand traffic for different objective function schemes in the R‑NOMA‑BF system. We can observe that the schemes of transferring objective problem from difference function to ratio function make the gaps larger. The constraint \(R_i \leq D_i\) of scheme 2 has a significant influence on the natural fit compared to 1 for mNOMA. More specifically, the traffic gap of the D‑mNOMA‑BF algorithm changes upward by 1.10 dB from scheme 1 to 2, and A‑mNOMA‑BF rises at 1.02 dB. The other phenomenon is that both the A‑eNOMA‑BF and D‑eNOMA‑BF algorithms do not differ much, yet they, respectively, improved in 0.75 and 0.66 dB for both schemes as users demand increased up to 1100 Mbps. Accordingly, the second‑order function of discrete difference better suits the algorithms proposed above. Scheme 2 is restricted to \(R_i \leq D_i\), indicating that users' satisfaction is weakened in the case of slight lost traffic. The proposed algorithms show good adaptive and generalization capabilities among different metrics.

![Figure 9: Objective traffic gap versus error radio of ipSIC with multiple antenna numbers.](图片占位符_Fig9)

Fig. 9 plots objective traffic gap versus error radio of ipSIC with multiple antenna numbers, where \(0 \leq \kappa_i \leq 1\) is introduced to denote the ipSIC factor. The user interference of the first decoding is not completely eliminated in the cell. Hence, the interference of users in the R‑NOMA‑BF system is rewritten as

\[\sum_{j\in \mathcal{N}\backslash \{i\}}|\mathbf{h}_i^H\mathbf{w}_j|^2 p_j + \sum_{j\in \mathcal{N}\backslash \{i\}}|\mathbf{h}_i^H\mathbf{w}_j|^2 p_j\kappa_i. \quad (29)\]

Since the exponential cone programming cannot iterate power \(p_i\) with pSIC through (26), the yellow and blue curves are plotted for the D‑mNOMA‑BF and A‑mNOMA‑BF algorithms from antenna number 4, and 8 to 16, respectively. As observed, when \(\kappa_i\) exceeds \(10^{-3}\), the D‑mNOMA‑BF and A‑mNOMA‑BF algorithms with \(L = 16\) become a better option. Elevated \(\kappa_i\) means that target users receive more interference from decoding users first. Besides, the lower number of antennas is unable to make a dramatic change in the performance of the A‑mNOMA‑BF algorithm. This phenomenon shows that the antenna number affects BF vector optimization enabling more accurate interference isolation, where energy in different directions is concentrated according to (9). As the array response vectors get more accurate, user capacities are raised. The increased number of antennas takes into account the phased array antenna size and layout changes on the satellite side, where the size of the flat plate, the number, and arrangement of array elements are included. In addition, intelligent satellite processors are regarded as an important method to enhance data processing capability.

![Figure 10: Minimum traffic satisfaction rate versus satellite ID with various comparative algorithms in the R‑NOMA‑BF system.](图片占位符_Fig10)

Fig. 10 plots the bar graph of the minimum traffic satisfaction rate versus LEO satellite ID in the R‑NOMA‑BF system. The minimum traffic satisfaction rate is defined as \(\max_{k}\{\min \{\frac{B_k}{D_k}, 1\}\}\) for each LEO satellite, which implies the worst capacity‑demand mismatch between the LEO satellite and users. It can be observed that the A‑eNOMA‑BF algorithm outperforms the other benchmarks with high traffic satisfaction for each satellite. Moreover, in the A‑eNOMA‑BF algorithm, the minimum traffic satisfaction rate for LEO satellite 1 is one, i.e., all users in satellite 1 are satisfied. A lower minimum traffic satisfaction rate indicates a smaller percentage of satisfied users for the satellite service. In addition, the modified ant colony algorithms all outperform the performance of the Doppler‑shift‑based algorithms. A conclusion can be drawn that the modified ant colony algorithm is more effective in global optimization.

![Figure 11: Energy efficiency versus satellite transmission power with different algorithms.](图片占位符_Fig11)

Fig. 11 plots the energy efficiency versus satellite transmission power with different algorithms in the R‑NOMA‑BF system. The energy efficiency is defined as the ratio of the information transmission rate to the transmit power, i.e., \(\sum_{m \in \mathcal{M}} \frac{\sum_{i \in \mathcal{M}} \log(1 + \gamma_i)}{P_m^{tot}}\). \(P_m^{tot}\) represents the sum of power allocated to users by each satellite. As can be observed, with increasing satellite transmission power, the D‑eNOMA‑BF and A‑eNOMA‑BF algorithms approach a maximum of energy efficiency at the power of 25 dBW. This indicates that the energy efficiency cannot always keep growing with power due to the indirect effects of user traffic requests and interference. In addition, in contrast to OMA and LEO satellite communication without relay satellite assistance algorithms, the proposed algorithms have significantly higher performance in terms of energy efficiency. The relay satellite can reduce the energy consumption of LEO satellite nodes and ground stations, while the NOMA‑based algorithms can effectively avoid the waste of power resource.

---



# ASTARS Aided NOMA Covert Communication Networks

This section provides simulation results to confirm the theoretical insights covered in earlier subsections. The key simulation parameters are listed in Table I. Furthermore, parameter \(U\) is chosen as \(10^3\) to strike a balance between complexity and accuracy. The output powers of ASTARS and PSTARS are respectively denoted by \(P_{act} = P_A - P_{tn} - M(P_{con} + P_{amp})\) and \(P_{\mathrm{pas}} = P_A - MP_{con}\) [21], where \(P_{tot}\) is the total power budgets, \(P_{tn} = -10\) dBm is the thermal noise power, \(P_{con} = -20\) dBm is the power consumption of the ASTARS phase shift control circuit, \(P_{amp} = -20\) dBm is the power consumption of the ASTARS amplifier. The AWGN at user \(\beta\) is denoted as \(\sigma_D^2 = -90\) dBm. Additionally, we establish two comparison baselines, namely PSTARS‑NOMA and ASTARS‑OMA. For the PSTARS‑NOMA network, the power amplification factor is \(\mu = 1\) and the thermal noise control factor is \(\nu = 0\), while other parameters are configured the same as in the ASTARS‑NOMA network [32]. For the ASTARS‑OMA network, we set \(P_{act}^{OMA} = 0.5P_{act}\) to ensure an objective comparison.

**TABLE I**  
THE PARAMETERS FOR SIMULATION RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^6\) iterations |
| The power allocation factors for two users | \(a_r = 0.3\), \(a_t = 0.7\) |
| The detection threshold for two users | \(\tau = -40\) dB |
| The distance from Alice to user \(r\) | \(d_{ar} = 20\) m |
| The distance between Alice and ASTARS | \(d_{as} = 20\) m |
| The distance between ASTARS and user \(r\) | \(d_{sr} = 10\) m |
| The distance between ASTARS and \(w_r\) | \(d_{sw_r} = 10\) m |
| The distance between ASTARS and user \(t\) | \(d_{st} = 10\) m |
| The distance between ASTARS and \(w_t\) | \(d_{sw_t} = 10\) m |
| The path loss control factor | \(\alpha = 2\) |

![Figure 2: False alarm probability versus ASTARS output power \(P_{act}\) with \(M = 5\), \(\tau = -40\) dBm and \(\mu = 100\).](图片占位符_Fig2)

Fig. 2 plots the false alarm probability versus ASTARS output power \(P_{act}\) with \(M = 5\) and \(\tau = -40\) dBm. The false alarm probability of \(w_r\) and \(w_t\) for ASTARS/PSTARS are plotted using (17) and (26), respectively. This illustration confirms that the analytical expressions derived perfectly align with the simulation outcomes, thereby substantiating the precision of the analytical approaches employed. It is evident that the covert effectiveness of ASTARS‑NOMA covert networks greatly exceeds that of ASTARS‑OMA, attributable primarily to two key factors: 1) The thermal noise and AWGN of ASTARS‑OMA convert networks do not cover the transmission messages well without the help of NOMA protocol. The warden can easily detect the transmission of covert messages, which also verifies Remark 1. 2) ASTARS‑NOMA is capable of achieving better fairness in false alarm probabilities among paired users. Another phenomenon is that whether in the transmission region or the reflection region, the false alarm probability of ASTARS‑NOMA increases faster than that of PSTARS‑NOMA. This phenomenon indicates that the ASTARS configuration has ability to increase warden's detecting error probability, enhancing the overall security and reliability of covert communications. The superiority of ASTARS can be attributed to its optimized phase shift capabilities and more efficient signal processing, which improve the system capability to mask the covert transmissions against surveillance attempts. Another observation is that ASTARS‑NOMA is \(5\) dBm higher than PSTARS‑NOMA in reflection region and \(7\) dBm higher in transmission region. This occurs due to ASTARS elements that simultaneously amplify the power of the public messages and thermal noise to mask the covert message.

![Figure 3: Miss detection probability versus ASTARS output power \(P_{act}\) with \(M = 5\), \(\tau = -40\) dBm and \(\mu = 100\).](图片占位符_Fig3)

Fig. 3 plots the curve of the miss detection probability versus ASTARS output power \(P_{act}\) with \(M = 5\) and \(\tau = -40\) dBm. The black and pink solid curves represent miss detection probability of \(w_r\) and \(w_t\) for ASTARS‑NOMA which are plotted based on (18) and (27), respectively. It is observed that the miss detection probabilities of ASTARS‑NOMA and PSTARS‑NOMA are equal to one in the low \(P_{act}\) region. With the increase of \(P_{act}\), the miss detection probability converges to zero. Another observation is that the miss detection probability of ASTARS‑NOMA in the reflection region decreases faster than that of in the transmission region. This is because that reflection region warden \(w_r\) can also use the direct link channel to obtain stronger transmission power of user \(r\) covert message, making \(w_r\) judgment more accurate.

![Figure 4: False alarm probability versus ASTARS output power \(P_{act}\) with \(\tau = -70\) dB, \(\mu = 10\) and \(\rho_r = 0.8\).](图片占位符_Fig4)

Fig. 4 plots the false alarm probabilities of \(w_r\) and \(w_t\) versus ASTARS output power \(P_{act}\) for \(M = \{5,10,15\}\) with setting to be \(\tau = -70\) dBm, \(\mu = 10\) and \(\rho_r = 0.8\). It can be observed that as the number of ASTARS elements \(M\) increases, the slope of the false alarm probability gradually rises. This is because as \(M\) increases, thermal noise also increases as a new coverage medium, better covers covert communications, which verifies Remark 2.

![Figure 5: Miss detection probability versus ASTARS output power \(P_{act}\) with \(\alpha = 2\), \(\tau = -20\) dB, \(\mu = 10\) and \(\rho_r = 0.8\).](图片占位符_Fig5)

Fig. 5 plots the miss detection probability versus \(P_{act}\) for different \(M\) values with \(\alpha = 2\), \(\tau = -20\) dBm, \(\mu = 10\) and \(\rho_r = 0.8\). As can be seen that with the number of \(M\) growing, the slope of the miss detection probability increases and the network's concealment performance deteriorates. This is due to the fact that large number of ASTARS elements increase the transmission power while simultaneously increasing the risk of exposure in covert communications. Consequently, it is crucial to consider the impact of the number of ASTARS elements when deploying practical ASTARS‑NOMA covert networks.

![Figure 6: DEP versus \(P_{act}\) with \(M = 10\) and \(\mu = 50\).](图片占位符_Fig6)

Fig. 6 plots the DEP of ASTARS‑NOMA versus \(P_{act}\) for different values of \(\tau\) with \(M = 10\) and \(\mu = 50\). The simulation DEP curves for wardens in ASTARS/PSTARS‑NOMA obtained through Monte Carlo simulations, are in complete agreement with the analytical results of (19), (20), (28) and (29). An important observation is that as \(P_{act}\) increases, the DEP of \(w_r\) first decreases smoothly and then increases. This can be briefly explained as follows: When \(P_{act}\) is low, the miss detection probability is the dominant factor in DEP. With the values of \(P_{act}\) increases, the false alarm probability becomes the dominant factor in DEP. In addition, the DEP of \(w_t\) shows a decreasing trend as \(P_{act}\) increases. This is because the transmission region lacks a direct link with Alice resulting in lower received signal strength for \(w_r\), which increases the miss detection probability. One can notice that with an increase in the detection threshold \(\tau\), the DEP curves for the wardens tend to move rightward. This is because the rate of increase of the miss detection probability is faster than the rate of decrease of the false alarm probability leading to a decrease in DEP. As observed from figure that each \(\tau\) corresponds to a minimum DEP which verifies Remark 4. We can also observe that under the same power conditions, ASTARS‑NOMA has higher energy efficiency compared to PSATRS‑NOMA. This is because ASTARS uses internal thermal noise to confuse the warden without the need to introduce additional random noise.

![Figure 7: DEP versus power allocation coefficient \(a_r\) for different \(M\).](图片占位符_Fig7)

Fig. 7 plots the DEP curves of ASTARS‑NOMA versus power allocation coefficient \(a_r\) for different number of ASTARS elements \(M\) with \(P_{act} = 25\) dBm, \(\mu = 10\), \(a_t = 1 - a_r\), where PSTARS‑NOMA is selected as the baseline for comparison. It is noticeable that the DEP of \(w_r\) with ASTARS‑NOMA surpasses that observed in PASTARS‑NOMA. However, when \(a_r > 0.8\) the DEP will rapidly decrease, meaning that the probability of user \(r\) being detected will significantly increase. The primary cause of this effect is that assigning additional power to user \(r\) raises the likelihood of the covert message being detected. Another phenomenon is that the DEP of \(w_t\) is more advantageous than PSTARS‑NOMA when \(a_r > 0.35\). Therefore, setting \(a_r\) in the range \([0.3, 0.5]\), not only allow users achieve better covert effect but also align with the fairness requirements of NOMA communications.

![Figure 8: Covert transmission rate versus \(P_{act}\) with \(a_t = 0.7\), \(a_r = 0.3\) and \(\mu = 100\).](图片占位符_Fig8)

Fig. 8 plots the covert transmission rates of ASTARS‑NOMA versus \(P_{act}\) with \(a_t = 0.7\), \(a_r = 0.3\) and \(\mu = 100\). The covert transmit rate of ASTARS‑NOMA networks is plotted according to (32), (33) and (34), respectively. It is evident that the covert transmission rate of user \(r\) with ipSIC/psIC for ASTARS‑NOMA outperforms that in PSTARS‑NOMA networks. This occurs because ASTARS's ability to amplify signal strength helps user \(r\) boost the network's average data transmission rate. It is evident that at high SNRs, the covert transmission rate of user \(r\) with pSIC in ASTARS‑NOMA rises significantly, which validates Remark 5. Notably, the covert communication rate of user \(t\) levels off at high SNRs, aligning with the throughput ceiling, thereby supporting the conclusion in Remark 6.

![Figure 9: Covert transmission rate versus \(P_{act}\) with different ASTARS elements.](图片占位符_Fig9)

In addition, Fig. 9 plots the covert transmit rate versus \(P_{act}\) with different ASTARS elements. With the increase in ASTARS elements, the covert communication rate of user \(r\) in ASTARS‑NOMA networks, utilizing pSIC/pSIC, exhibits more noticeable changes compared to the rate of user \(t\). In particular, user \(t\) becomes more sloped as the number of ASTARS elements increases, which doesn't raise the throughput ceiling.

![Figure 10: System throughput versus \(P_{act}\) in delay‑tolerant transmission mode.](图片占位符_Fig10)

Fig. 10 plots the system throughput of ASTARS‑NOMA and ASTARS‑OMA versus \(P_{act}\) in delay‑tolerant transmission model, with \(M = 10\), \(\tau = -70\) dBm and \(\mu = 10\). It is apparent that the system throughput of ASTARS‑NOMA covert networks remains stable at high SNRs, with the throughput ceiling rising as residual interference diminishes. An additional observation is that raising the internal thermal noise intensity of ASTARS elements leads to a reduction in the throughput of ASTARS‑NOMA with pSIC. The reason for this is that higher thermal noise intensity results in a lower SNR, making it harder for the receiver to decode the signal. Therefore, developing a hardware architecture that minimizes power consumption and interference is crucial for enhancing the covert performance of ASTARS‑NOMA networks.

---



# Secure Communication of Active RIS Assisted NOMA Networks

In this section, numerical results are presented to confirm the accuracy of the closed‑form expressions under both external and internal eavesdropping scenarios. To facilitate notational presentation, the simulation parameters utilized are given in Table I [54], [65], where BPCU indicates the abbreviation for bit per channel use. Note that the values of \(|h_{ipu}|^2\) and \(|h_{ipe}|^2\) closely relate to the power of the signal received by the users. Specifically, about \(1/7\), \(1/70\) and \(1/700\) of user \(m\)'s signal power are taken as the residential interference during user \(n\)'s SIC process [35]. In addition, since the reconfigurable elements on ARIS are small and closely spaced [18], the fading characteristics of the cascaded channels corresponding to each reconfigurable element differ very little from each other, so all the attenuation factors are set to the same value. In future studies, especially for large‑scale ARIS scenarios, we will relax this assumption and consider the impact of the variation of the attenuation factor on each ARIS element on the secrecy performance of ARIS‑NOMA networks. To highlight the secrecy performance of ARIS‑aided NOMA networks, the PRIS‑aided networks, AF relay, and half‑duplex (HD)/FD‑DF relay communication schemes are considered as benchmarks, which share the same total power budget as ARIS‑aided NOMA networks.

**TABLE I**  
THE TABLE OF MONTE CARLO SIMULATION PARAMETERS

| Parameter types | Values |
|-----------------|--------|
| The pathloss factors | \(\alpha = 2\), \(\beta = -30\) dB |
| The AWGN power | \(\sigma^2 = \sigma_e^2 = -55\) dBm |
| The hardware power consumption | \(P_{PS} = P_{DC} = -10\) dBm |
| The power allocation coefficients | \(a_f = 0.7\), \(a_n = 0.3\) |
| The target secrecy rates for users | \(R_f = R_n = 0.05\) BPCU |
| The distance from BS to ARIS | \(d_{br} = 20\) m |
| The distance from ARIS to users/Eves | \(d_{rf} = d_{rn} = 20\) m, \(d_{rn} = 10\) m |

### A. External Wiretapping Scenario

![Figure 2: The SOP versus system power budget under ARIS‑NOMA and PRIS‑NOMA networks in external eavesdropping scenarios, with \(M = 40\), \(P = 2\) and \(Q = 20\).](图片占位符_Fig2)

Fig. 2 plots the SOP versus system power budget under external eavesdropping scenario, where the secrecy performance of PRIS‑NOMA networks is taken into account for comparison. The theoretical analysis curves for user \(f\) and user \(n\) with ipSIC/pSIC are obtained from (29), (27) and (28), respectively. It is obvious to see that the Monte Carlo simulation results are consistent with the analytical results during the entire range of power budget. In the high SNR region, analysis curves can converge exactly to the asymptotic SOP lines based on (44), (34) and (40), which also manifests the validity of the theoretical expressions. We can observe that ARIS‑NOMA networks can achieve lower SOP than PRIS‑NOMA networks. This is because that active reconfigurable elements can further amplify the input radio signals \(\kappa\) times larger by allocating a portion of the system power budget to these components. Hence, the higher SNR can be received at users and thus strengthen the secure communication. Moreover, the error floors appear for ARIS‑NOMA networks with ipSIC. This is due to the residential interference caused by ipSIC, which also matches with the conclusions in Remark 1.

![Figure 3: The SOP versus system power budget under ARIS‑NOMA, ARIS/PRIS‑OMA and conventional relaying schemes in external eavesdropping scenarios, with \(M = 40\), \(P = 2\), \(Q = 20\) and \(R_{OMA} = 0.1\) BPCU.](图片占位符_Fig3)

Fig. 3 plots the SOP versus system power budget under external eavesdropping scenario, where the secrecy performance of ARIS/PRIS‑OMA networks, AF relay and HD/FD‑DF relay schemes are surveyed as benchmarks. One can observe from the figure that the secrecy performance of ARIS‑NOMA networks exceeds that of ARIS‑OMA, AF relay, HD‑DF and FD‑DF communication schemes. The reasons are explained as follows: 1) The higher utilization rate of spectrum can be acquired in ARIS‑NOMA networks since NOMA is able to superpose multiple signals together within the same resource block; and 2) ARIS is able to adjust the phase shifts and amplitudes of the incident signals, which remarkably improve the electromagnetic environment and enhance the quality of channel conditions around.

![Figure 4: The system SOP versus different number of reconfigurable elements under external eavesdropping scenario, with \(P_{tot} = -40\) dBm, \(\sigma_t^2 = -40\) dBm and \(|h_{ipu}|^2 = |h_{ipe}|^2 = -80\) dB.](图片占位符_Fig4)

Fig. 4 plots the system SOP versus different number of reconfigurable elements under external eavesdropping scenario. The analysis curves are plotted according to (29), (27), (28), respectively. We can observe that the system SOP of ARIS‑NOMA networks drops first and then level off at stable values with the growth of the number of active reconfigurable elements. This is due to the fact that introducing more active components are able to improve the freedom of spatial design, however, excessive reconfigurable elements can also mix lots of thermal noise in the received signals, which is not conducive to users decoding their own signals and counteracts the channel gain brought by the spatial freedom. Another observation is that larger values of \(\kappa\) lead to the decline in the system SOP for ARIS‑NOMA networks with ipSIC. The main reason behind this phenomenon is that more power will be occupied at ARIS since the value of \(\kappa\) rises gradually and it can directly weaken the unfavorable effect caused by residential interference. On the contrary, decreasing \(\kappa\) is beneficial to the system secrecy performance of ARIS‑NOMA with pSIC. This is because the thermal noise brought by active elements holds the main station of the received interference in pSIC situation. Obviously, applying smaller \(\kappa\) can effectively lower the detrimental noise and provide users with superior SNR to resist eavesdropping.

![Figure 5: The SOP versus system power budget under external eavesdropping scenario, with \(M = 40\), \(P = 2\), \(Q = 20\) and \(|h_{ipu}|^2 = |h_{ipe}|^2 = -80\) dB.](图片占位符_Fig5)

Fig. 5 plots the SOP versus system power budget under external eavesdropping scenario. We define \(\alpha_P \in (0,1)\) as the power offset factor and the power allocation coefficients for user \(f\) and user \(n\) can be given by \(a_f = \alpha_P\) and \(a_n = 1 - \alpha_P\), respectively. As can be observed from the figure that the system secrecy performance of ARIS‑NOMA networks dips gradually with the increase of \(\alpha_P\). The reason is that fairness can be achieved for both non‑orthogonal users by allocating the far user \(f\) with more power in ARIS‑NOMA networks, which is helpful to preserve the secure transmission. Another observation is that the system SOP begin to climbing since \(\alpha_P\) reaches 0.8 and even more. This is because that overlarge value of \(\alpha_P\) will seriously encroach on the power allocated to the near user \(n\) and break the fairness between both users. As a consequence, the system SOP start to show signs of getting worse. This suggests that it is pivotal to set suitable power allocation coefficients in ARIS‑NOMA networks to guarantee secure communication.

![Figure 6: The system secrecy throughput versus system power budget under external eavesdropping scenario, with \(M = 60\), \(\kappa = 20\) and \(|h_{ipu}|^2 = |h_{ipe}|^2 = -80\) dB.](图片占位符_Fig6)

Fig. 6 plots the system secrecy throughput versus system power budget under external eavesdropping scenario. The curves for ARIS‑NOMA with ipSIC/pSIC can be obtained from (27), (28), (29) and (45), respectively. It is observed from the figure that ARIS‑NOMA networks are capable of achieving higher system secrecy throughput than PRIS‑NOMA networks before convergence. This is because the amplification function offers ARIS‑NOMA superior secrecy outage performance, which leads to the larger secrecy throughput. Another observation is that the throughput of ARIS‑NOMA decreases when the parameters vary from \(Q = 10\), \(P = 6\) to \(Q = 30\), \(P = 2\) at the beginning and increase in the high system power budget region. This phenomenon can be explained that setting more active components to one will deepen the interference caused by thermal noise since the distortion from ipSIC is not apparent at first. However, the negative effects brought by residual interference gradually dominate with the sharp rise of the system power budget, and adjusting more elements to one benefits alleviating the harmful influence of ipSIC. That is, values of \(Q\) and \(P\) are set largely depending on the prevailing type of interference. This kind of mutual suppression relationship between thermal noise and residual interference is also manifested in the analysis of Fig. 4, which makes the gap of ARIS‑NOMA less obvious compared to that of PRIS‑NOMA with the variation of \(Q\) and \(P\).

![Figure 7: The system secrecy throughput versus amplification factor under external eavesdropping scenario, with \(M = 40\) and \(R_n = R_f = 0.1\) BPCU.](图片占位符_Fig7)

Fig. 7 plots the system secrecy throughput versus amplification factor under external eavesdropping scenario. One can observe from the figure that the secrecy throughput is able to realize a remarkable development via expanding the scope of system power budget. This is due to the fact that sufficient power budget is helpful to improve the received SNR at users and thus enhance the anti‑eavesdropping capability, which is also in accordance with the analysis of Fig. 2 and Fig. 3. Another observation is that the gap in terms of secrecy throughput between ipSIC and pSIC is negligible with the growth of amplification factor \(\kappa\). The reason is that the effect of thermal noise on throughput performance will exceed that of residual interference and the latter can even be neglected when \(\kappa\) keeps rising. This can also be utilized to explain the phenomenon that a larger \(\kappa\) is required to bridge the gap caused by ipSIC when the residual interference changes from -80 dBm to the severe -70 dBm.

### B. Internal Wiretapping Scenario

![Figure 8: The SOP versus system power budget under internal eavesdropping scenario, with \(M = 40\), \(P = 2\), \(Q = 20\) and \(|h_{ipu}|^2 = |h_{ipe}|^2 = -80\) dB.](图片占位符_Fig8)

Fig. 8 plots the SOP versus system power budget under internal eavesdropping scenario. The theoretical analysis curves for user \(n\) with ipSIC and pSIC are plotted based on (31) and (32), respectively, which match with the simulation results. The effectiveness of SOP expressions are also verified by the asymptotic lines. It can be seen from the figure that the secrecy performance of ARIS‑NOMA networks is superior to that of PRIS‑NOMA networks. The reason is that active elements can uniquely amplify the power of incident signals and thus enhance the secure transmission. One can also observe that the SOP deteriorates gradually with the increase of thermal noise generated by the active components. This can be explained that larger value of \(\sigma_t^2\) impairs the received SNR at user \(n\), which can impose a negative effect on the secrecy performance of ARIS‑NOMA networks.

![Figure 9: The SOP versus system power budget under internal eavesdropping scenario, with \(M = 40\), \(P = 2\), \(Q = 20\) and \(|h_{ipu}|^2 = |h_{ipe}|^2 = -70\) dB.](图片占位符_Fig9)

Fig. 9 plots the SOP versus system power budget under internal eavesdropping scenario. It is can be seen from the figure that the system secrecy outage behaviours are becoming better with the decrease of \(\alpha_P\), which is the direct opposite of the observation in Fig. 5. The reason is that user \(f\) with poor channel condition is regarded as the internal Eve and a lower power allocation coefficient can impair the quality of received signals and reduce the wiretapping abilities.

![Figure 10: The system secrecy throughput versus system power budget under internal eavesdropping scenario, with \(M = 40\), \(P = 2\), \(Q = 20\), \(R_n = 0.15\) BPCU and \(|h_{ipu}|^2 = |h_{ipe}|^2 = -70\) dB.](图片占位符_Fig10)

Fig. 10 plots the system secrecy throughput versus system power budget under internal eavesdropping scenario. The curves for ARIS‑NOMA networks with ipSIC and pSIC can be obtained according to (31), (32) and (46), respectively. One can make the following observation from figure that ARIS‑NOMA networks can always achieve superior secrecy throughput performance to PRIS‑NOMA networks with arbitrary system power budget. The reason is that the additional amplification brought by active components significantly reduces the SOP as displayed in Fig. 8, which makes it possible for ARIS‑NOMA to reach higher secrecy throughput. Furthermore, we can observe that the secrecy throughput performance becomes worse with the advancement in residential interference. This phenomenon indicates that more precise hardware design should be implemented at transceivers since the grim influence of ipSIC can bring seriously impairment to the secrecy throughput performance under internal eavesdropping scenario.

---



# Secrecy Performance Analysis of RIS Assisted Ambient Backscatter Communication Systems

In this section, numerical results are presented to verify the derivations in Section III. For the convenience of notation, the simulation parameters adopted are summarized in Table I [22], [38], where BPCU represents the abbreviation for bit per channel use. Noise power at LU and Eve is given by \(\sigma_u^2 = \sigma_e^2 = -170 + 10\log(f_c) + N_f = -90\) dB, where the bandwidth is set to \(10\) MHz and noise figure is \(10\) dB [53]. To highlight the secrecy performance of RIS‑AmBC networks, the conventional AmBC networks without RIS and jammer‑based AmBC networks are both taken into account as benchmarks. Note that the jammer‑based model and simulation setups are in accordance with [26], where the RIS is replaced with a traditional backscatter device and a cooperative jammer is settled in the cell radiating artificial noise and confusing the Eve.

**TABLE I**  
THE TABLE OF MONTE CARLO SIMULATION PARAMETERS

| Parameter | Value |
|-----------|-------|
| Pathloss factor | \(\lambda = 2\) |
| Frequency dependent factor | \(\eta = -30\) dB |
| AWGN power | \(\sigma_u^2 = \sigma_e^2 = -90\) dBm |
| Efficiency of transmitting power amplifier | \(\theta = 0.32\) |
| Residential interference | \(\Omega_{ipu} = \Omega_{ipe} = -90\) dBm |
| Target secrecy rate for data signal | \(R_u = 0.5\) BPCU |
| Target secrecy rate for backscatter signal | \(R_c = 0.1\) BPCU |
| Distance from the source to RIS/LU/Eve | \(d_{sr} = d_{su} = 20\) m, \(d_{se} = 30\) m |
| Distance from RIS to LU/Eve | \(d_{ru} = 10\) m, \(d_{re} = 20\) m |
| Hardware static power consumption | \(\{P_u, P_{sw}^{hw}, P_{rws}^{hw}, P_{AmBC}^{hw}\}\) |

![Figure 2: SOP versus transmitting power in RIS‑AmBC networks.](图片占位符_Fig2)

Fig. 2 plots the SOP versus transmitting power in RIS‑AmBC networks, where \(P = 2\), \(\rho_e = 20\) dBm and \(\kappa = 0.5\). The theoretical analyses and simulations are well matched. On one hand, we can see that the SOP of the backscatter signal is much lower compared to conventional AmBC networks. This is because RIS can enhance the cascaded channel condition to improve the reliability of wireless propagation. On the other hand, as the power of backscatter signal increases, the SINR of LU decoding its own data signal decreases according to (3), so that the SOP of the data signal in the traditional AmBC networks is lower than that of the data signal in RIS‑AmBC networks. In addition, it is can be observed that when the transmission power is sufficient, the jammer‑based secure transmission scheme outperforms the proposed scheme. This is because both the BS and the jammer have enough power to transmit data signals and interfere with Eve's eavesdropping behavior, without worrying about the negative impact of power being shared with each other. However, thanks to the cascaded link gain brought by RIS, the SOP of the backscatter signal in the RIS‑AmBC network is significantly lower than that in the jammer‑based AmBC network.

From the perspective of systemic SOP, it can be seen from Fig. 2 that the overall outage behaviour of RIS‑AmBC networks is better than that of the AmBC networks without RIS assistance. We can also observe that with increasing the number of RIS elements, the secrecy performance of backscatter signal is promoted while that of the data signal is degraded. The reason for this phenomenon is that more RIS elements provide greater reflecting channel gains for backscatter communication links. Based on this, the backscatter signal is regarded as interference by LU when it detects the data signal. Hence, increasing RIS elements is beneficial to improve the received SINR of backscatter signal, but weakens that of data signal. In addition, the error floors appear in the curves of data and backscatter signals with ipSIC demonstrated in Remark 1 and Remark 2.

![Figure 3: The SOP versus the number of RIS elements in RIS‑AmBC networks.](图片占位符_Fig3)

Fig. 3 plots the SOP versus the number of RIS elements, where \(P = 2\), \(R_u = R_c = 0.5\) BPCU, \(P_s = 30\) dBm, \(\rho_e = 20\) dBm and \(\kappa = 0.3\). It can be seen from the figure that with the rising value of \(\kappa\), the SOP of the backscatter signal keeps declining. This is because more power is absorbed to convey the backscatter signal and the reception quality of backscatter signal is improved. As the number of RIS elements increases, the system SOP of RIS‑AmBC networks first falls and then rises. This is due to the fact that the backscatter signal power is weak at first. By increasing the number of RIS elements, the received power of backscatter signal is gradually strengthened. However, the LU's ability to decode the data signal is greatly impaired when the power of the backscattered signal is too large, which in turn affects the system SOP performance.

![Figure 4: The SOP versus the horizontal distance of RIS in RIS‑AmBC networks.](图片占位符_Fig4)

Fig. 4 plots the SOP versus the horizontal distance of the RIS in RIS‑AmBC networks, where \(M = 12\), \(P = 2\), \(P_s = 20\) dBm and \(\kappa = 0.5\). For purposes of illustration, the locations of the BS, LU, Eve and the RIS are labelled as (0, 0), (20 m, 0), (30 m, 0) and \((x_{RIS}, 2)\) respectively in Euclidean coordinate space, where \(x_{RIS}\) denotes the horizontal height of the RIS and varies from \(1\) m and \(20\) m. From Fig. (a) we can observe that the SOP of the backscatter signal is lower when the RIS is deployed close to the BS/LU. This is due to the fact that when the RIS is in the middle between the BS and the user, the incident and reflecting signals suffer from strong multiplicative fading, which impairs the secrecy rate of the backscatter signal. Furthermore, it can be seen from Fig. (b) that the optimal SOP for RIS‑AmBC networks under pSIC can be achieved at the middle position \((x_{RIS} = 10\) m) regardless of the wiretapping capability of Eve. This is due to the fact that the SOP of the backscatter signal with pSIC is much lower than that of the data signal, which means that the SOP of RIS‑AmBC networks depends mainly on the data signal. According to Fig. 2, the data signal and the backscatter signal are just offset from each other, which results in the RIS being best deployed in the center for RIS‑AmBC networks with pSIC. However, the SOP of the backscatter signal with pSIC increases significantly and together with the data signal affects the overall performance of RIS‑AmBC networks. In this case, the RIS can be deployed slightly closer to the BS or LU (e.g., \(x_{RIS} = 4, 14\) m).

![Figure 5: The secrecy throughput versus transmitting power in RIS‑AmBC networks.](图片占位符_Fig5)

Fig. 5 plots the secrecy throughput versus transmitting power, where \(M = 12\), \(P = 2\), \(R_u = 1\), \(R_c = 0.7\) BPCU, \(\rho_e = 20\) dBm and \(\kappa = 0.3\). It is observed that the secrecy throughput of RIS‑AmBC networks with pSIC/ipSIC can not reach the theoretical upper limit (1.7 BPCU). This is because that the backscatter signal and residual interference can both corrupt LU's decoding process and result in error floors, so the SOP of data and backscatter signal will not be zero even with high SNRs. Furthermore, we can also observe that the secrecy throughput is impaired when the level of ipSIC increases. The reason for this is that the LU's received SINR is reduced and the resistance to eavesdropping is weakened.

![Figure 6: The secrecy throughput versus the horizontal distance in RIS‑AmBC networks.](图片占位符_Fig6)

Fig. 6 plots the secrecy throughput versus the horizontal distance of the RIS in RIS‑AmBC networks, where \(M = 12\), \(P = 2\), \(P_s = 20\) dBm and \(\kappa = 0.5\). On one hand, it can be seen from the figure that regardless of the level of Eve's SNR, deploying the RIS midway between the BS and the LU is the optimal strategy to obtain the maximum secrecy throughput of RIS‑AmBC networks. This can be explained by the fact that the target rate of the data signal occupies a larger share of the throughput and the SOP of the data signal is lower when the RIS is located near \(x = 10\) m. On the other hand, considering the analyses of the relationship between SOP and RIS deployment locations in Fig. 4, the RIS can also be deployed slightly closer to the BS or LU (e.g., \(x_{RIS} = 6, 12\) m) with a little acceptable loss of secrecy throughput under the practical ipSIC scenarios. In addition, we can observe that residual interference caused by ipSIC attenuates the SINR of the LU when decoding the backscatter signal, thus compromising the safe throughput of RIS‑AmBC networks.

![Figure 7: The secrecy throughput versus the number of RIS elements in RIS‑AmBC networks.](图片占位符_Fig7)

Fig. 7 plots the secrecy throughput versus the number of RIS elements in RIS‑AmBC networks, where \(P = 2\), \(P_s = 40\) dBm, \(R_u = 1\) and \(R_c = 0.1\). As can be seen from the figure that increasing the reflecting coefficient \(\kappa\) reduces the secrecy throughput of RIS‑AmBC networks. As \(\kappa\) increases, the amplification of the backscatter signal occurs, consequently compromising the SINR for LU during data signal decoding. Additionally, the system throughput is predominantly impacted by the data signal rate. Moreover, the observed trend indicates an initial rise and subsequent decline in the secrecy throughput of RIS‑AmBC networks concerning variations in the number of RIS elements. The reason for this is that there exists an optimal value of \(M\) that minimises the SOP according to Fig. 3 and this in turn will also lead to the existence of a value of \(M\) that maximises secrecy throughput in delay‑limited transmission mode.

![Figure 8: The secrecy energy efficiency versus transmitting power in RIS‑AmBC networks.](图片占位符_Fig8)

Fig. 8 plots the secrecy energy efficiency versus the transmitting power in RIS‑AmBC networks., where \(M = 4\), \(P = 2\), \(P_s = 40\) dBm, \(\rho_e = 10\) dBm, \(\kappa = 0.3\), \(R_u = 1\) and \(R_c = 0.1\) BPCU. As the transmitting power rises, the secrecy energy efficiency gradually decreases after reaching a peak. This is due to the fact that according to Fig. 5, the secrecy throughput of RIS‑AmBC networks tends to converge in the high transmitting power region, i.e., the numerator in (42) has an upper bound, while the transmitting power in the denominator part continues to increase, so the secrecy energy efficiency drops after reaching a maximum. In addition, when Eve has a high level of wiretapping (\(\rho_e = 15\) dBm), RIS‑AmBC networks require a larger transmitting power to keep the secrecy rate stable in order to reach the optimal security energy efficiency.

---



# Performance Analysis of Double Reconfigurable Intelligent Surfaces Assisted NOMA Networks

In this section, simulations are provided to verify the accurateness of equations derived form the above sections. The fixed numerical values of the parameters are indicated in TABLE I, and BPCU is the abbreviation of bit per channel use. To show the enhancement of PRIS‑ARIS‑NOMA, PRIS‑ARIS‑OMA and double PRISs‑NOMA are presented as benchmark. We have borrowed the simulation approach from [23] and [38], and combined it with the model in this paper, and the validation results of the numerical part are similar to those of these two papers, thus verifying the feasibility of communication in this scenario. For OMA scheme, we assume the transmission of users information is orthogonal in the frequency domain, and each of the two users occupies half of the frequency domain resource. To ensure fairness, the total power consumption of each system is meant to be the same. Specifically, the total power consumption of PRIS‑ARIS‑NOMA and double PRISs‑NOMA are respectively presented as \(Q_{total}^{active} = P_s^a + P_{ar} + (M + N)P_{sw} + MP_{dc}\) and \(Q_{total}^{passive} = P_s^p + (M + N)P_{sw}\), where \(P_s^p\) means the transmitting power of the base station for double PRISs‑NOMA, \(P_{ar}\) means the output signal power of ARIS while \(P_{sw}\) and \(P_{dc}\) respectively represent the power consumption of the phase shift switch and control circuit in each reflecting element and the DC bias power of each reflecting element on ARIS [45]. Then it can be defined as \(P_{to} = Q_{total}^{active} = Q_{total}^{passive}\). The complexity‑accuracy trade‑off parameters are set to be \(P = I = U = 500\), \(K = 100\). For simulation parameter settings, it can be referred from [33], [37], and [40].

**TABLE I**: The fixed numerical values of the parameters.

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulation repeated | \(10^6\) iterations |
| Rician factor | \(\kappa = -5\) dB |
| Shaping parameter | \(m_{na} = 1\) |
| Amplification factor | \(\beta = 2.5\) |
| Number of reflecting elements | \(M = N = 3\) |
| Communication link distance | \(d_{h1} = d_{g1} = 10\) m, \(d_{h2} = d_{gn} = 20\) m, \(d_{gm} = 80\) m |
| Two users power allocations | \(a_n = 0.2\), \(a_m = 0.8\) |
| Two users target rates | \(R_n = 2\) BPCU, \(R_m = 2\) BPCU |
| Noise power | \(\sigma^2 = -80\) dBm, \(\sigma_a^2 = -70\) dBm |
| Path loss factors | \(\alpha = 2\), \(\eta = -10\) dBm |

### A. Outage Probability

![Figure 2: Outage probability versus the transmitting power of the BS for PRIS‑ARIS‑NOMA.](图片占位符_Fig2)

Fig. 2 depicts the outage probability of PRIS‑ARIS‑NOMA versus the transmitting power of the BS, and also compares the outage probability of \(D_n\) with different residual interference power under the ipSIC scheme and the outage probability of the two users under OMA networks. As shown in the figure, the curves of outage probability for \(D_n\) with ipSIC/pSIC and \(D_m\) can be plotted in terms of (13), (14) and (16), while the curves of outage probability for user \(D_n\) and user \(D_m\) under OMA networks can be plotted in terms of (19). And the curves for asymptotic outage probability can be plotted in terms of (21), (22) and (24). It can be observed from the figure that the theoretical value curve is highly coincident with the simulation, thus verifying the correctness and applicability of the theoretical derivation. For the user's outage performance, it can be read from the picture that the NOMA networks outperform the OMA networks and reflect the fact that NOMA can provide better user fairness than OMA when there are channel differences between users [55]. Consistent with Remark 1, the outage probability of \(D_n\) with ipSIC eventually gets to an error floor for the impact of the residual interference, and \(D_n\) with ipSIC scheme will get a better outage performance as the residual interference power decreases. Hence, it is crucial to take the residual interference into consideration when it comes to a practical communication scenario.

![Figure 3: Outage probability versus the total power consumption.](图片占位符_Fig3)

Fig. 3 depicts the outage probability for the comparison of PRIS‑ARIS‑NOMA and double PRISs‑NOMA versus the total power consumption of the networks with settings of \(\Omega_{RI} = -80\) dBm. In this case, the outage probability of users without RISs assistance scenario is also plotted in the figure, and it can be seen that the user outage performance of the communication link without RISs assistance is poor in this communication environment. As can be observed from the figure that the outage performance of PRIS‑ARIS networks is better than the double PRISs networks, the cause of this phenomenon is that ARIS is equipped with active bias circuitry compared to PRIS and has a built‑in signal amplifier to increase the signal power, which helps improve the user's reception SNR at the receiving end. It also reflects that the use of ARIS can better combat fading in the channel with the comparison to PRIS.

![Figure 4: Outage probability versus the transmitting power of the BS for PRIS‑ARIS‑NOMA.](图片占位符_Fig4)

Fig. 4 depicts the outage probability of PRIS‑ARIS‑NOMA versus the transmitting power of the BS with settings of \(\Omega_{RI} = -80\) dBm, and compares users outage probability with different reflecting elements. From the trend of outage probability in the figure, we can find that as the number of RISs reflecting elements increases, the users will tend to get a better outage performance. This is because that the number of reflecting elements determines the number of independent divisions of the transmission, and as the number of independent divisions increases, the ability of the signal to fight against channel fading increases by a certain degree, so the users outage performance becomes better. Meanwhile, in line with Remark 2 and Remark 3, the diversity orders of \(D_n\) and \(D_m\) are affected by the reflecting elements on RISs. Therefore, as the number of reflecting elements \(M\) increases, the users outage probability curves gain a larger slope and decrease faster.

![Figure 5: Outage probability versus the transmitting power of the BS for PRIS‑ARIS‑NOMA.](图片占位符_Fig5)

Fig. 5 depicts the outage probability of PRIS‑ARIS‑NOMA versus the transmitting power of the BS with settings of \(\Omega_{RI} = -80\) dBm, and compares users outage probability with different shaping parameter \(m_{na}\) of Nakagami‑\(m\) random variables. From the figure, it can be intuitively observed that the outage performance of users gradually becomes better as \(m_{na}\) increases. This is because the physical meaning of \(m_{na}\) in the communication scenario represents the depth of channel fading, with larger \(m_{na}\) indicating shallower channel fading and higher communication quality of the communication channels. Theoretically, when \(m_{na}\) tends to 0, it means communication is almost impossible to achieve, and when \(m_{na}\) tends to infinity, it means no fading exists in the communication channels. It can also be observed from the figure that the variation of \(m_{na}\) does not affect the slope of the users outage probability, which is due to the fact that the user's diversity order depends only on the reflecting elements number of ARIS, which coincides with the Remark 2 and Remark 3.

![Figure 6: Outage probability versus the transmitting power of the BS for PRIS‑ARIS‑NOMA over long‑distance transmission scenario.](图片占位符_Fig6)

In order to demonstrate the advantages of this system model for long‑distance transmission, we also analyzed a scenario of PRIS‑ARIS‑NOMA networks for long‑distance transmission as shown in Fig. 6. In this scenario, the distance between the communication links is set as \(d_{h1} = d_{h2} = d_{g1} = 1000\) m, \(d_{gn} = 800\) m, \(d_{gm} = 1800\) m respectively, and the number of reflecting elements used by the two RISs grows moderately as well. From the figure, it can be seen that the PRIS‑ARIS‑NOMA networks has a significant enhancement of the communication performance for long‑distance transmission, and the users outage probabilities can reach a threshold of \(10^{-3}\) at a transmitting power around \(5\) dBm. Also as the number of reflecting elements increases, the outage probability decreases more rapidly, which confirms the insights obtained from the Remark 2 and Remark 3.

### B. Ergodic Data Rate

![Figure 7: Ergodic data rate versus the transmitting power of the BS for PRIS‑ARIS‑NOMA.](图片占位符_Fig7)

Fig. 7 depicts the ergodic data rate of PRIS‑ARIS‑NOMA versus the transmitting power of the BS with settings of \(\Omega_{RI} = -80\) dBm, and also compares the ergodic data rate of \(D_n\) and \(D_m\) under OMA networks. As shown in the figure, the curves of ergodic data rate for \(D_n\) with ipSIC/pSIC and \(D_m\) can be plotted in terms of (27), (28) and (29), while the curves of ergodic rate for user \(D_n\) and user \(D_m\) under OMA networks can be plotted in terms of (30). And the curves for asymptotic ergodic data rate can be plotted in terms of (32), (33) and (34). The figure shows that the ergodic data rate of \(D_n\) with ipSIC and \(D_m\) eventually converge to an upper throughput limit and converge to a zero ergodic data rate slope at high SNR region, which are in lines with the Remark 4 and Remark 6. This is because for \(D_n\) with ipSIC, it is similar to the analysis of the outage probability, self interference affects the users receiving performance more as the transmitting power increases. And for \(D_m\), upper throughput limit is only dependent on the power allocation factors of the two users according to (34). Moreover, the ergodic performance of \(D_n\) with ipSIC under NOMA networks is better than that of the OMA networks. For OMA networks, the division of resources for per user in the frequency domain is reduced by one‑half compared to NOMA systems, so the ergodic data rate slope of the OMA networks is reduced by one‑half compared to NOMA networks, which is the reason why the ergodic data rate under OMA networks grows slower than that of the NOMA networks.

![Figure 8: Ergodic data rate versus the total power consumption.](图片占位符_Fig8)

Fig. 8 depicts the ergodic data rate for the comparison of PRIS‑ARIS‑NOMA and double PRIS‑NOMA versus the total power consumption of the networks with settings of \(\Omega_{RI} = -80\) dBm. One can be seen is that the ergodic data rates of \(D_n\) with ipSIC/pSIC and \(D_m\) in PRIS‑ARIS‑NOMA are superior to that in double PRIS‑NOMA, this is because that ARIS amplifies and forwards the signals through the built‑in bias circuit, which can increase the SINR at the receiving end, so the ergodic data rate will be higher.

![Figure 9: Ergodic data rate versus the transmitting power of the BS for PRIS‑ARIS‑NOMA.](图片占位符_Fig9)

Fig. 9 depicts the ergodic data rate for PRIS‑ARIS‑NOMA versus the transmitting power of the BS with settings of \(\Omega_{RI} = -80\) dBm, and compares the ergodic data rate of the two users under different number of reflecting elements of the ARIS. From the figure we can observe that as the number of ARIS reflecting elements increases, the ergodic data rate gradually increases.

### C. System Throughput

![Figure 10: System throughput versus the total power consumption.](图片占位符_Fig10)

Fig. 10 depicts the system throughput for the comparison of PRIS‑ARIS‑NOMA and double PRISs‑NOMA versus the total power consumption of the networks in delay‑limited transmission mode with settings of \(\Omega_{RI} = -80\) dBm. The curves for the system throughput in delay‑limited transmission mode can be drawn in terms of (25). It can be observed from the figure that the system throughput of the PRIS‑ARIS‑NOMA in delay‑limited transmission mode is higher than that of the double PRISs networks and OMA networks. This is due to the fact that the system throughput in delay‑limited transmission mode is relevant to the system outage probability and a lower outage probability yields a higher throughput. Another phenomenon is that the system throughput with ipSIC scheme cannot reach the maximum value. This is because residual interference limits the extent to which the outage probability decreases with increasing transmitting power, thus producing an upper limit on the system throughput that does not reach the expected maximum value.

![Figure 11: System throughput versus the transmitting power of the BS for PRIS‑ARIS‑NOMA.](图片占位符_Fig11)

Fig. 11 depicts the system throughput for PRIS‑ARIS‑NOMA versus the transmitting power of the BS in delay‑tolerant transmission mode with settings of \(\Omega_{RI} = -80\) dBm. The curves for the system throughput in delay‑tolerant transmission mode can be drawn in terms of (35). From the figure, we can observe that the throughput of the system can be improved by increasing the number of RIS reflecting elements and reducing the power of self interference under the ipSIC scheme. It also reflects the importance of optimizing the SIC process in NOMA networks.

---



# Exploiting Active RIS in NOMA Networks With Hardware Impairments

In this section, the numerical results are provided to verify the effectiveness of analytical results for ARIS‑NOMA networks. We also consider the impact of HIS on outage probability, ergodic data rate and energy efficiency of ARIS‑NOMA networks. The noise power and bandwidth are set to be \(\sigma^2 = -174 + 10\log (BW)\) and \(BW = 1000\) MHz respectively. For illustration purposes, the simulation results used are concluded in Table I [25], [39], where the abridgement of BPCU denotes bit per channel use. To facilitate comparison, PRIS‑NOMA‑HIS, PRIS‑OMA‑HIS are regarded as benchmarks for ARIS‑NOMA‑HIS. In addition, conventional cooperative communication schemes, i.e., multi‑antenna AF relaying is also selected to compare the behaviour of ARIS‑NOMA/OMA‑HIS.

Something deserving of clarification is that to demonstrate the accuracy of the results, we have kept the total power consumed by PRIS‑NOMA‑HIS and ARIS‑NOMA‑HIS the same. More specifically, \(P_{BS}^{ARIS} = P_{BS}^{ARIS} + P_{RIS}^{ARIS} + L(P_{SW} + P_{DC})\), \(P_{BS}^{PRIS} = P_{BS}^{PRIS} + LP_{SW}\) and \(P_{BS}^{ARIS} = P_{b}^{PRIS} = P_b\), where \(P_{BS}^{ARIS}\) and \(P_{BS}^{PRIS}\) are the transmit power of BS in ARIS and PRIS networks, \(P_{RIS}^{ARIS}\) is the signal output power in ARIS and \(P_{RIS}^{ARIS} = P_{BS}^{ARIS}\beta \| \Theta \mathbf{h}_{br}\|^2 + \beta N_{tn}\| \Theta \|^2\), \(P_{SW}\) indicates the amount of power used by each RIS element's control circuit and phase shift switches, \(P_{DC}\) means the direct current biasing power [40].

**TABLE I**  
SIMULATION PARAMETERS FOR ARIS‑NOMA

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^5\) iterations |
| The power allocation factors of user \(g\) and user \(f\) | \(a_g = 0.25\), \(a_f = 0.75\) |
| The targeted rates of user \(g\) and user \(f\) | \(R_g = 1.5\) BPCU, \(R_f = 1.5\) BPCU |
| The distance between BS and ARIS | \(d_{br} = 10\) m |
| The distance between ARIS and user \(g\) | \(d_{rg} = 10\) m |
| The distance between ARIS and user \(f\) | \(d_{rf} = 20\) m |
| The distance between ARIS and user \(o\) | \(d_{ro} = 30\) m |
| The reflection coefficient of ARIS | \(\beta = 5\) |
| The thermal noise power at ARIS | \(N_{tn} = -30\) dBm |
| The AWGN power at users | \(\sigma^2 = -20\) dBm |
| Pass loss expression | \(\alpha = 2.2\) |

![Figure 2: Outage probability versus the transmit power \(P_b\) with \(K = 3\), \(g = 3\), \(f = 2\), \(L = 5\), \(\beta = 5\) and \(m = 0.5\), \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig2)

Fig. 2 plots the outage probability of ARIS‑NOMA‑HIS networks versus \(P_b\) with \(K = 3\), \(g = 3\), \(f = 2\), \(L = 5\), \(\beta = 5\), \(m = 0.5\) and \(R_g = R_f = 1.5\) BPCU. It shows that the Monte Carlo simulation values of outage probability agree perfectly with the above theoretical analyses. We can find that the outage probability of user \(g\) with ipSIC congregates to an error floor at higher transmit power \(P_b\) which is identical to the conclusion in Remark 1. ARIS‑NOMA‑HIS outage performance outperforms that of ARIS‑OMA‑HIS because NOMA has higher fairness than OMA when serving multiple customers at the same time. Another critical finding is that ARIS‑OMA‑HIS outperforms DF and AF relay switching between full‑duplex (FD) and half‑duplex (HD) modes for outages at high SNRs. The reason for it is that ARIS enhances the signals reflected back to users. This indicates that even though ARIS generates amplified noise, its outage performance is still superior to that of traditional cooperative communications, i.e., HD/FD AF relaying.

![Figure 3: Outage probability versus the transmit power \(P_b\) with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(\beta = 5\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig3)

Fig. 3 plots the outage probability for ARIS‑NOMA/OMA‑HIS networks versus \(P_b\) for different values of the fading parameter \(m\) with \(K = 3\), \(L = 5\), \(g = 3\), \(f = 2\), \(\beta = 5\) and \(R_g = R_f = 1.5\) BPCU. It can be observed that the outage probability of ARIS‑NOMA‑HIS increases with the fading factor \(m\). As \(m\) becomes higher, i.e., \(m = 0.5\), 0.7 and 1, ARIS‑NOMA‑HIS networks are enabling improved outage performance. The main reason for this phenomenon is that larger values of \(m\) correspond to smaller channel fading, and when \(m \rightarrow \infty\) indicates no fading. It is worth noting that when \(m = 1\), the cascaded Nakagami‑\(m\) fading channel is converted to a Rayleigh fading channel.

![Figure 4: Outage probability versus the transmit power \(P_b\) with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.5\), \(\beta = 5\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig4)

As a further advance, Fig. 4 shows the impact of HIS on system outage performance. It is visible that the outage behaviors of ARIS‑NOMA‑HIS are in connection with the HIS. As \(\kappa\) increases, the gap between outage probabilities becomes larger at high SNRs. It takes \(P_b = 10\) to improve outage performance even if \(\kappa = 0.01\). The slope of the curve stays identical regardless of the value of \(\kappa\) changes. This phenomenon indicates that we can improve the outage behaviours of ARIS‑NOMA‑HIS by reducing the HIS.

![Figure 5: Outage probability versus the different distance between BS and ARIS, with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.5\), \(\beta = 5\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig5)

Fig. 5 plots the outage probability of ARIS‑NOMA/OMA‑HIS networks versus the different distance from BS to ARIS. Assuming that the BS is in the same plane as user \(g\) and user \(f\) and they are located at \((0,0)\), \((30,0)\) and \((40,-10)\) respectively. Besides, ARIS are located at \((x_{ARIS},10)\) where \(x_{ARIS}\) indicates the distance between BS and ARIS. It can be noted that the outage performance of user \(f\) is gradually deteriorating. The causes of this phenomenon is that as \(d_{rf}\) decreases, the increasing trend of denominator in (4) is much greater than numerator. In summary, ARIS deployed on BS side offers higher performance gains. In addition, reducing the thermal noise values \(N_{tn}\) does not improve the performance of ARIS‑OMA‑HIS networks.

![Figure 6: Outage probability versus the reflection elements number \(L\) with \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.5\), \(\beta = 10\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig6)

Fig. 6 plots the outage probability of ARIS‑NOMA‑HIS networks versus the different reflection elements number \(L\) with \(P_b = 20\) dBm, \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.5\), \(\beta = 10\) and \(R_g = R_f = 1.5\) BPCU. One can observe that initially both ARIS‑NOMA‑HIS and PRIS‑NOMA‑HIS achieve better performance when \(L\) rises. However, as \(L\) increase to a certain level, the outage performance of ARIS‑NOMA‑HIS starts to deteriorate. The reason for this phenomenon is that as \(L\) increases, thermal noise from ARIS becomes larger. This means that ARIS‑NOMA‑HIS networks performs about similar as PRIS‑NOMA‑HIS networks when there are fewer reflective elements. It is worth considering the trade‑off between reflection elements number of ARIS and outage performance.

![Figure 7: Outage probability versus the reflection amplitude factors, with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig7)

Fig. 7 plots the outage probability of ARIS‑NOMA/OMA‑HIS networks versus the different reflection amplitude factors \(\beta\) with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\) and \(R_g = R_f = 1.5\) BPCU. It can be seen that as \(\beta\) increases, the outage performance gain gradually reaches saturation. This is because that as \(\beta\) tends to infinity, the outage probability approaches a particular value. Moreover, the gain in outage probability for the ARIS‑NOMA‑HIS networks with pSIC is more pronounced when \(P_b\) is increased from \(25\) dBm to \(30\) dBm.

![Figure 8: System throughput versus the transmit power \(P_b\) with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig8)

Additionally, Fig. 8 plots the system throughput versus the transmit power \(P_b\) in delay‑limited case with \(L = 5\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\) and \(R_g = R_f = 1.5\) BPCU. The system throughput of ARIS‑NOMA‑HIS is plotted on the basis of (26). As can be observed that ARIS‑NOMA‑HIS is able to reach throughput ceiling earlier than PRIS‑NOMA‑HIS. The throughput ceiling of ARIS/PRIS‑NOMA‑HIS with ipSIC is lower than that with pSIC because of the residual interference from ipSIC. The system throughput of ARIS‑NOMA‑HIS is far more favourable than that of PRIS‑NOMA‑HIS and ARIS‑OMA‑HIS. The major contributing factors is that ARIS‑NOMA‑HIS networks have better spectral efficiency and the capability to offer service for multiple users.

![Figure 9: Rate versus the transmit power \(P_b\) with \(L = 2\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\), \(\beta = 5\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig9)

Fig. 9 plots the ergodic data rates versus the transmit power \(P_b\) with \(L = 2\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\), \(\beta = 5\) and \(R_g = R_f = 1.5\) BPCU. We can observe that the ergodic data rate for the ARIS‑NOMA‑HIS networks is still higher than that for PRIS‑NOMA‑HIS. Future more, ARIS‑NOMA‑HIS with ipSIC achieves a weaker rate than that with pSIC. As \(P_b\) increases, the rate for user \(f\) gradually reaches the upper bound and this is in alignment with the findings in Remark 4 and Remark 5.

![Figure 10: Rate versus the transmit power \(P_b\) with \(L = 2\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\) and \(R_g = R_f = 1.5\) BPCU.](图片占位符_Fig10)

Fig. 10 plots the ergodic data rates versus the transmit power \(P_b\) in delay‑tolerate schemes with \(L = 2\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.7\) and \(R_g = R_f = 1.5\) BPCU. The influence of changing the HIS factor \(\kappa\) on ergodic data rate of system was plotted, which basing on (41). We can observe that as \(\kappa\) increases, i.e., from 0.08 to 0.15, the ergodic performance degradation in ergodic data rate increases, and is more pronounced in ARIS/PRIS‑NOMA‑HIS with pSIC. At the same time, the ergodic data rate reached an upper ceiling due to the effects of HIS. This demonstrates the importance of accurately modeling HIS values when evaluating ARIS‑NOMA networks. Moreover, the residual interference from ipSIC has no significant effect on ARIS‑NOMA‑HIS networks when \(P_b\) is lower.

![Figure 11: Energy efficiency in delay‑tolerant and delay‑limited transmission mode, with \(L = 2\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.5\) and \(R_g = R_f = 1.5\) BPCU. (a) Delay‑tolerant mode. (b) Delay‑limited mode.](图片占位符_Fig11)

Fig. 11(a) and (b) plot the energy efficiency curves in delay‑tolerant and delay‑limited transmission modes with \(L = 2\), \(K = 3\), \(g = 3\), \(f = 2\), \(m = 0.5\) and \(R_g = R_f = 1.5\) BPCU, respectively. Fig. 11(a) shows the delay‑tolerant transmission model of ARIS/PRIS‑NOMA‑HIS networks. It can be observed that ARIS‑OMA‑HIS and PRIS‑OMA‑HIS have lower energy efficiency and that of the ARIS‑NOMA‑HIS networks is significantly improved compared to PRIS‑NOMA‑HIS. As can be seen the system's energy efficiency begins to deteriorate at \(P_b > 15\) dBm, This can be inferred by the fact that the total power consumption of the system becomes larger as \(P_b\) increases. Furthermore, the energy efficiency of the ARIS‑NOMA‑HIS dramatically increases as the growth of the reflection amplification \(\beta\). This conclusions can also be applied in delay‑limited schemes. The difference is that the energy efficiency of ARIS‑NOMA‑HIS with ipSIC is significantly worse than that with pSIC. This demonstrates how delay‑limited systems are substantially more sensitive to residual interference from ipSIC than delay‑tolerant ones. As the weak trend of ARIS‑NOMA‑HIS networks indicates its stability in transmitting information.

---



# Active Simultaneously Transmitting and Reflecting Surface Assisted NOMA Networks

This section provides the computer simulation results to verify the correctness of theoretical formulas in Sections III and IV. The simulation settings used, unless otherwise specified, are displayed in Table I. The complexity‑accuracy trade‑off parameters i.e., \(K\), \(Q\) and \(U\) are set to \(10^3\). To highlight the performance of ASTARS‑NOMA networks, the ARIS‑NOMA, ASTARS‑OMA and PSTARS‑NOMA are selected as benchmarks. In particular, the total power budgets of ASTARS and PSTARS‑aided networks are respectively given by \(Q_{tot}^{act} = P_s^{act} + P_{ri}^{act} + L(P_c + P_d)\) and \(Q_{tot}^{pas} = P_s^{pas} + LP_c\) [37], [39], where \(P_{ri}^{act}\) is the output signal power of ASTARS/ARIS, the power used by the phase shift control circuit in each active element is \(P_c = -20\) dBm and the direct current bias power used by the amplifier placed in each ASTARS/ARIS element is indicated as \(P_d = -20\) dBm. To achieve the purpose of fairness comparisons, \(Q_{tot}^{act}\) is set to be the same as \(Q_{tot}^{pas}\). Moreover, in ARIS‑NOMA networks, to obtain \(360^\circ\) coverage, we employ a surface made up of one transmit‑only RIS and one reflect‑only RIS [57]. In addition, we employed the frequency division multiple access scheme to transmit signals of \(U_r\) and \(U_t\) in two separate bandwidth resources, and the achievable rate for the OMA scheme can be denoted as \(\frac{1}{2}\log (1 + \lambda \beta_r \rho_s |\mathbf{h}_r^H \Phi_r \mathbf{h}_s|^2)\), where \(\rho_s = \frac{P_s^{act}}{\lambda \beta_r |\mathbf{h}_r^H \Phi_r \mathbf{h}_s|^2 + \sigma_0^2}\). At this point, the target SNR for the OMA scheme is set to \(2^{2R_r} - 1\).

**TABLE I**  
SIMULATION PARAMETERS FOR ASTARS‑NOMA NETWORKS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^6\) iterations |
| Rician factor | \(\kappa = -5\) dB |
| Amplification factor | \(\lambda = 5\) |
| Number of ASTARS elements | \(L = 10\) |
| Coverage radius of ASTARS | \(D = 35\) m |
| Distance from BS to ASTARS | \(d_s = 50\) m |
| Amplitude coefficients of ASTARS elements | \(\beta_r = 0.7, \beta_t = 0.3\) |
| The power allocation factors of \(U_r\) and \(U_t\) | \(a_r = 0.3, a_t = 0.7\) |
| Noise power | \(\sigma_s^2 = -70\) dBm, \(\sigma_0^2 = -90\) dBm |
| Pass loss factors | \(\alpha = 2, \eta_0 = -30\) dB |
| Target data rates for \(U_r\) and \(U_t\) | \(\hat{R}_r = 1\) BPCU, \(\hat{R}_t = 1\) BPCU |

### A. Outage Probability

![Figure 3: Outage probability of ASTARS‑NOMA versus system power budget \(Q_{tot}\).](图片占位符_Fig3)

In Fig. 3, we plot the outage probability of \(U_r\) and \(U_t\) versus the system power budget. The outage probability curves of \(U_t\) and \(U_r\) with pSIC/ipSIC curves are plotted by (14), (15) and (17), respectively. This figure demonstrates that the analytical expressions derived match the simulation results exactly, which validates the accuracy of the analytical methods applied. The blue dotted lines for asymptotic outage probability are plot based on (22), (23) and (24), respectively. They perfectly match the outage probability curves of ASTARS‑NOMA networks at high SNRs, proving that the asymptotic approaches used are accurate. One can observe that the outage performance of \(U_r\) with pSIC and \(U_t\) for ASTARS‑NOMA networks outperforms that of ASTARS‑OMA networks. This is due to the fact that NOMA enables higher spectrum efficiency and better user fairness. Another phenomenon is that as \(Q_{tot}\) exceeds \(30\) dBm, the outage behaviors of \(U_r\) with ipSIC for ASTARS‑NOMA is worse than that of ASTARS‑OMA. It also converges to an error floor in the high SNR region. With the increasing of residual interference value, the outage probability of \(U_r\) with ipSIC becomes much more larger compared to pSIC. This is attributed that the outage probability of \(U_r\) for ASTARS‑NOMA networks suffers from residual interference caused by ipSIC, which confirms the conclusion in Remark 2.

![Figure 4: Outage probability of ASTARS‑NOMA versus BS's transmit power \(P_s^{act}\).](图片占位符_Fig4)

Moreover, Fig. 4 displays the outage probability of \(U_r\) and \(U_t\) for ASTARS‑NOMA networks versus transmit power of BS under \(L = \{3,6,9\}\). The figure shows that as the number of ASTARS elements rises, the outage probability falls and its slope rises. This phenomenon is caused by the fact that the diversity orders of \(U_t\) and \(U_r\) with pSIC are proportional to the number of ASTARS elements, which confirms the conclusions made in Remark 3 and Remark 4.

![Figure 5: Outage probability versus number of ASTARS/ARIS elements \(L\) with \(Q_{tot}^{act} = Q_{tot}^{pas} = 20\) dBm, \(\lambda = 10\) and \(\sigma_s^2 = -30\) dBm.](图片占位符_Fig5)

In Fig. 5, we plot the outage probability of ASTARS‑NOMA versus number of ASTARS elements \(L\), with \(Q_{tot}^{act} = Q_{tot}^{pas} = 20\) dBm, \(\lambda = 10\) and \(\sigma_s^2 = -30\) dBm. As can be observed that with ASTARS elements increase, the outage probability first decreases and then gradually increases. This trend can be attributed to the complex interactions between various factors. On the one hand, the introduction of more ASTARS elements can enhance the spatial degrees of freedom and thus reduce the outage probability. This is because that the increased degrees of freedom enable a more efficient use of spatial domain, resulting in better signal quality and stronger channel gains. On the other hand, using too many ASTARS elements can lead to a large amount of thermal noise, which severely hinders the user's ability to decode the signal. This counteracts the channel gains generated by spatial degrees of freedom and leads to a surge in outage probability. Hence, the optimization of ASTARS‑NOMA networks is a balance between the numbers of active component and the spatial degrees of freedom, with the ultimate goal of minimizing outage probability.

![Figure 6: System outage probability versus system power budget \(Q_{tot}\).](图片占位符_Fig6)

Fig. 6 displays the system outage probability of ASTARS‑NOMA and different benchmarks versus the system power budget. One can observe that the system outage performance of ASTARS‑NOMA outperforms that of ASTARS‑OMA, which can be explained by the following two reasons: 1) The power allocation strategy employed by NOMA demonstrates a significant advantage over the bandwidth‑splitting scheme of OMA; 2) The performance of ASTAR‑NOMA networks can be further enhanced by the better compatibility between ASTARS and NOMA. As can be shown that the outage performance of ASTARS‑NOMA performs better than that of PSTARS‑NOMA. This can be interpreted that the ASTARS elements allocate a portion of power budget to amplify the input radio signals, which enhances the received SNR at paring users. This also confirms that ASTARS is an effective technology for combating multiplicative fading loss. One occurrence is that ASTARS‑NOMA achieves better outage performance than ARIS‑NOMA. In addition, the outage curves of ASTARS‑NOMA are steeper than those of ARIS‑NOMA. This can be explained by the fact that ASTARS is able to achieve a better diversity order than ARIS [57].

![Figure 7: System outage probability versus reflection amplitude coefficient with \(P_s^{act} = 30\) dBm.](图片占位符_Fig7)

In Fig. 7, we show the system outage probability of ASTARS‑NOMA versus reflection amplitude coefficient under \(Q_{act} = 30\) dBm, where ARIS‑NOMA is selected as the baseline for comparison. The curves of outage probability for ASTARS‑NOMA is plotted according to (20). It is worth noting that the reflection/transmission coefficients satisfy the constraint \(\beta_t = 1 - \beta_r\). Thus, \(\beta_r = 0.5\) represents the minimal difference in channel conditions, while positions closer to the ends of the \(X\)-axis indicate greater differences in channel conditions. From the figure, we can observe that the points with the lowest outage probability are all located within intervals \((0.1,0.5)\) and \((0.5,0.9)\). This suggests that ASTARS can increase the variability of channel conditions by adjusting the reflection/transmission coefficients, which further enhances the performance of NOMA networks. However, the larger differences in channel conditions do not mean that the higher performance can be obtained [58], [59]. For instance, ASTARS‑NOMA performs even worse than ARIS‑NOMA when \(\beta_r = 0.1\) and \(\beta_r = 0.9\). This is because that a low system outage probability requires a low outage probability for both users in the system. Assigning more reflection/transmission coefficients to one of the users means that the other user will have an increased outage probability. Therefore, optimizing the reflection/transmission coefficients is crucial for reducing the outage probability of ASTARS‑NOMA networks. Furthermore, we can observe that as the target rate gradually increases, the performance of ASTARS‑NOMA decreases accordingly. This is due to the fact that the larger target rate increase the quality of service requirements, resulting in a more challenging to successfully decode the signals.

![Figure 8: Outage probability versus amplification factor \(\lambda\) with \(P_s^{act} = 25\) dBm and \(\sigma_s^2 = -50\) dBm.](图片占位符_Fig8)

In Fig. 8, we plot the system outage probability of ASTARS‑NOMA versus amplification factor \(\lambda\), with \(P_s^{act} = 25\) dBm and \(\sigma_s^2 = -50\) dBm. One phenomenon is that the outage probability of ASTARS‑NOMA first reduces dramatically as the amplification factor steadily rises and then tends to stabilize. This is due to the fact that the larger amplification factors helps to improve the users' received SNR, thus enhancing the outage performance. However, while increasing the received signal strength at the users, also introduces a large amount of thermal noise, which interferes with the decoding of user signals. As the amplification factor increases, a balance is achieved between the gain of the enhanced signal and the loss of the enhanced noise such that the outage probability remains constant. Another observation is that reducing the deployment range of users improves outage performance. This is because that a smaller deployment range diminishes the effect of path loss on the ASTARS‑NOMA's outage probability. From these insights, we can discern that a larger power amplification factor does not necessarily translate to better outage performance. Therefore, in practical applications, it's advisable to calculate the minimum power amplification factor that achieves optimal performance, thereby reducing the load on the equipment.

### B. Ergodic Data Rate

![Figure 9: Ergodic data rate versus system power budget \(Q_{tot}\) with \(a_r = 0.2\), \(a_t = 0.8\).](图片占位符_Fig9)

In Fig. 9, we present ergodic data rate of ASTARS‑NOMA and PSTARS‑NOMA versus system power budget with \(a_r = 0.2\), \(a_t = 0.8\). The ergodic data rate curves for ASTARS‑NOMA networks are drawn from (27), (28) and (29), respectively. According to (31), (33) and (34), the asymptotic ergodic data rates are illustrated. This figure indicates that the \(U_t\)'s ergodic data rate converges towards the upper limit of the throughput, resulting in zero high SNR slope. The ergodic data rate of ipSIC stops increasing with a rise in transmit power at high SNRs due to the effects of residual interference, which in accordance with the discussion in Remark 5. One phenomenon is that the \(U_r\)'s ergodic data rates with pSIC/ipSIC of ASTARS‑NOMA are higher than those of PSTARS‑NOMA. This is due to the fact that ASTARS is able to increase the strength of users' received signals, which further increase the average data transmission rate of networks over an extended period. Another phenomenon is that the ergodic data rates of ASTARS‑NOMA with a larger power amplification factor is more efficient. This is because, although increasing the power amplification factor enhances the strength of the received signal as well as the power of thermal noise, the overall transmission SNR still experiences a certain level of improvement. As a result, when the power amplification factor is raised from 10 to 15, the ergodic data rate of ASTARS‑NOMA experiences an enhancement.

![Figure 10: Ergodic data rate versus system power budget \(Q_{tot}\) with \(a_r = 0.2\), \(a_t = 0.8\).](图片占位符_Fig10)

Fig. 10 compares the ergodic data rates of ASTARS‑NOMA with ARIS‑NOMA and ASTARS‑OMA. This figure indicates that the \(U_r\)'s ergodic data rate with pSIC/ipSIC of ASTARS‑NOMA outperform that of ARIS‑NOMA and ASTARS‑OMA. For the OMA transmission, it takes twice as long to serve two users as NOMA transmission. As a result, the slope of OMA transmission is only half of that of NOMA transmission, which is the reason for its lower ergodic data rate. The reason why ARIS‑NOMA networks have lower ergodic data rate compared to ASTARS‑NOMA networks is that they cannot provide the same spatial degrees of freedom as ASTARS networks do. Another phenomenon is that the ergodic data rate of \(U_t\) for ASTARS‑NOMA outperforms ARIS‑NOMA at low SNRs, while they reach the same upper limit of rate within high SNR region. This can be explained by using the conclusion of Remark 7 that the upper limit of \(U_t\)'s ergodic data rate in the NOMA network is related to the power allocation factors.

![Figure 11: Ergodic data rate versus system power budget \(Q_{tot}\) with \(a_r = 0.2\), \(a_t = 0.8\).](图片占位符_Fig11)

Additionally, Fig. 11 plots the ergodic data rate of ASTARS‑NOMA networks versus system power budget with different path loss exponents, i.e., \(\alpha\). In ASTARS‑NOMA networks, \(\alpha\) is a parameter to describe the signal power attenuation as it propagates through the wireless channels. A few real‑world channel models are to be adopted, depending on the choice of \(\alpha\). For example, \(\alpha = 2\) denotes the free space propagation case, \(\alpha = 2.5\) denotes the scenario with obstacles and \(\alpha = 3\) denotes the urban cellular networks. One can observe that as \(\alpha\) increases, the channel conditions of ASTARS‑NOMA networks become progressively worse, resulting in a deterioration of outage performance. Hence, grasping and computing path loss factors is essential in the design and enhancement of wireless communication systems. This aspect becomes particularly critical in the realms of mobile communication, satellite communication, and wireless local area network design. By precisely estimating path loss, it becomes possible to more efficiently strategize network coverage, select the optimal transmission power, and enhance the overall performance of the system.

### C. System Throughput

![Figure 12: System throughput versus system power budget \(Q_{tot}\) under delay‑limited transmission.](图片占位符_Fig12)

In Fig. 12, we present the system throughput of ASTARS‑NOMA with pSIC/ipSIC versus system power budget in the delay‑limited transmission mode. According to (25), the system throughput curves of ASTARS‑NOMA with pSIC/ipSIC are drawn. One phenomenon is that the system throughput of ASTARS‑NOMA outperform other comparison baselines under pSIC scheme. This is attributed to the fact that outage probability under delay‑limited transmission model determines the throughput of ASTARS‑NOMA networks. It can also be seen that the NOMA networks with ipSIC fail to reach the target rate even when the transmit power is large. This is due to the fact that residual interference limits the performance gains from increasing transmit power at high SNRs.

![Figure 13: System throughput versus system power budget \(Q_{tot}\) under delay‑tolerant transmission.](图片占位符_Fig13)

Fig. 13 shows the system throughput of ASTARS‑NOMA versus system power budget in the delay‑tolerant transmission model, with \(a_r = 0.2\), \(a_t = 0.8\) and \(\alpha = 2.3\). According to (35), the system throughput curves of ASTARS‑NOMA with pSIC/ipSIC schemes are shown. Under the ipSIC scheme, ASTARS‑NOMA exhibits a ceiling on system throughput, which diminishes as the strength of the residual interference increases. This occurs because, under ipSIC, the ergodic rate of ASTARS‑NOMA no longer gains from increased transmit power in high SNR regions, but rather reaches the throughput ceiling as demonstrated in (31). Observing (31), it becomes readily apparent that this throughput ceiling is inversely proportional to the intensity of the residual interference. Another phenomenon is that reducing the noise intensity generated by active devices can improve the system throughput of ASTARS‑NOMA with pSIC. This is due to the direct impact of thermal noise intensity on the magnitude of the decoding SNR of ASTARS‑NOMA with pSIC. Therefore, the design of low‑power and low‑interference hardware architecture is essential to improve the performance of ASTARS‑NOMA.

---



# Simultaneously Transmitting and Reflecting Reconfigurable Intelligent Surface Assisted NOMA Networks

In this section, we provide the simulation results to verify the theoretical analysis results derived in the above subsections for STAR‑RIS‑NOMA networks. The impacts of configurable elements \(K\) and Rician factor \(\kappa\) on the performance of STAR‑RIS‑NOMA are taken into account carefully. For notational simplicity, Table II has summarized the simulation parameters used in this paper, in which BPCU is the short for bit per channel use and the fixed power allocation of non‑orthogonal users considered is validity for the analytical expressions of outage probability and ergodic rate. Note that the choice of small target rates can be applied into the Internet of Thing scenarios, i.e., small packet service and so on. To guarantee the accuracy of approximate expressions, the complexity‑accuracy tradeoff parameters \(P\) and \(U\) are set to be \(P = 300\) and \(U = 50\), respectively. Without loss of generality, the conventional cooperative communication schemes, i.e., FD/HD DF and amplify‑and‑forward (AF) relaying and STAR‑RIS‑OMA are selected to be benchmarks for the purpose of comparison. It is worth pointing out that the entire communication process of STAR‑RIS‑OMA includes two time slots. In the first time slot, the BS sends the information \(x_n\) through RIS to reflect to user \(n\) and the BS sends \(x_m\) to transmit to user \(m\) via the assistance of RIS in the second slot. At this moment, the overall energy consumed of STAR‑RIS‑OMA is equal to that of STAR‑RIS‑NOMA from the perspective of comparison fairness.

**TABLE II**  
THE PARAMETERS FOR SIMULATION RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^6\) iterations |
| The power allocation factors for two users | \(a_n = 0.2\), \(a_m = 0.8\) |
| The targeted data rates for two users | \(R_n = 0.5\) BPCU, \(R_m = 0.5\) BPCU |
| The distance from BS to user \(n\) | \(d_{sn} = 10\) m |
| The distance from BS to STAR‑RIS | \(d_{sr} = 8\) m |
| The distance from STAR‑RIS to user \(n\) | \(d_{rn} = 6\) m |
| The distance from STAR‑RIS to user \(m\) | \(d_{rm} = 10\) m |
| Pass loss expression | \(\alpha = 2\) |

### A. Outage Probability

![Figure 2: Outage probability versus the transmit SNR, with \(K = 5\), \(\kappa = -5\) dB, \(R_n = 0.5\) and \(R_m = 0.5\) BPCU.](图片占位符_Fig2)

Fig. 2 plots the outage probability of STAR‑NOMA networks versus SNR with setting to be \(K = 5\), \(\kappa = -5\) dB, \(R_n = 0.5\) and \(R_m = 0.5\) BPCU. The diamond and right triangle solid curves for outage probability of user \(n\) with pSIC/ipSIC are plotted according to (14) and (15), respectively. The square curve for outage probability of user \(m\) is plotted based on (18). The left triangle and circle solid curves for outage probability of user \(n\) and user \(m\) for STAR‑RIS‑OMA are plotted based on (21) and (22), respectively. The outage probability curves are given by numerical simulation results and perfectly match with the theoretical analysis expressions derived in the above sections. One can observe that the outage behaviors of both user \(n\) with pSIC and user \(m\) for STAR‑RIS‑NOMA are superior to that of STAR‑RIS‑OMA. This is due to the fact that NOMA is capable of providing better fairness compared with OMA when multiple users are served simultaneously [4], [34]. The blue dotted curve for asymptotic outage probability of user \(n\) with pSIC/ipSIC and user \(m\) are plotted based on the theoretical results in (25), (26) and (27), respectively. The asymptotic outage probabilities of user \(n\) with ipSIC/pSIC and user \(m\) match the exact performance curves in the high SNR regime, which provides an effective performance evaluation method. As can be observed that the outage behavior of user \(n\) with pSIC outperforms that of user \(m\) for STAR‑RIS‑NOMA networks. The reason is that user \(n\) with pSIC can obtain the larger diversity order compared to user \(m\), which is in line with the insights in Remark 2. Due to the influence of residual interference, the outage probability of user \(n\) with ipSIC converges to an error floor and thus gain a zero diversity gain, which confirms the conclusion in Remark 1. Furthermore, with the increasing the value of residual interference, the outage performance of user \(n\) with ipSIC is becoming much worse in comparison with other users. Hence it is important to take into consideration these factors in actual communication scenarios.

![Figure 3: Outage probability versus the transmit SNR, with \(K = 5\), \(\kappa = -5\) dB, \(\mathbb{E}\{|h_I|^2\} = -30\) dB, \(R_n = 0.5\) and \(R_m = 0.5\) BPCU.](图片占位符_Fig3)

To explain the superiority of STAR‑RIS‑NOMA, Fig. 3 plots the outage probability of STAR‑NOMA networks versus SNR with different benchmarks. It can be observed that the outage behavior of STAR‑RIS‑NOMA with pSIC is superior to that of STAR‑RIS‑OMA and conventional cooperative communication systems, i.e., HD/FD DF relays [53], [55] and HD/FD AF relays [53], [56]. The main reasons are that 1) The FD DF/AF relays will be affected by loop residual interference, and it needs to use the advanced cancellation technology to eliminate the interference; 2) For HD DF/AF relays, STAR‑RIS‑NOMA networks work in FD mode and are not affected by loop interference; and 3) The STAR‑RIS‑NOMA has ability to provide the higher spectrum efficiency and user fairness relative to STAR‑RIS‑OMA. Additionally, the impact of channel estimation error, i.e., \(\Omega_e\) on system performance are taken into consideration in Fig. 3. One can observe that as the increase of channel estimate errors, i.e., from \(\Omega_e = -30\) dB to \(\Omega_e = -20\) dB, the outage probability of STAR‑RIS‑NOMA with pSIC is becoming much larger and also converge to the error floors at high SNRs. As a result, it is important to consider the effect of imperfect CSI when designing practical communication systems.

![Figure 4: Outage probability versus the transmit SNR, with \(\kappa = -5\) dB, \(\mathbb{E}\{|h_I|^2\} = -30\) dB, \(R_n = 2\) and \(R_m = 2\) BPCU.](图片占位符_Fig4)

Furthermore, Fig. 4 plots the outage probability of STAR‑RIS‑NOMA networks versus SNR with setting to be \(\mathbb{E}\{|h_I|^2\} = -30\) dB, \(R_n = 2\) and \(R_m = 2\) BPCU. We can be seen from the figure that as the number of configurable elements \(K\) grows, the outage probability of user \(n\) and user \(m\) for STAR‑RIS‑NOMA is getting much smaller and gain a steeper slope. This is because that the diversity orders of non‑orthogonal users are related to the configurable elements at the RIS, which is also in line with the conclusions in Remark 2 and Remark 3. This phenomenon indicates that it is prerequisite to adjust the number of configurable elements involved in the work according to the different service requirements.

![Figure 5: Outage probability versus the transmit SNR, with \(K = 5\), \(\mathbb{E}\{|h_I|^2\} = -30\) dB, \(R_n = 0.5\) and \(R_m = 0.5\) BPCU.](图片占位符_Fig5)

Fig. 5 plots the outage probability of STAR‑RIS‑NOMA networks versus SNR for the simulation with different Rician factors and \(\mathbb{E}\{|h_I|^2\} = -30\) dB. We can observe that the Rician factor i.e., \(\kappa\) has a relatively large impact on network performance of STAR‑RIS‑NOMA, where the outage probability of user \(n\) and user \(m\) decreases with the increasing of Rician factor values, i.e., \(\kappa = 0\) dB to \(\kappa = 5\) dB. This phenomenon can be explained that the LoS components of Rician fading channels dominate the network performance of STAR‑RIS‑NOMA. Another observation is that as the Rician factor grows, i.e., \(\kappa = -40\) dB to \(\kappa = 0\) dB, the outage probability of user \(n\) and user \(m\) for STAR‑RIS‑NOMA networks has minor changes. This is due to the fact that the cascade channels from the BS to RIS, and then RIS to user \(n\) and user \(m\) have been aligned by invoking coherent phase shifting, where the equivalent channels have a non‑zero mean. Additionally, it is worth pointing out that the channels between the BS and user \(n\) also include the direct link from the BS to user \(n\) except the cascade channels from BS to RIS, and then RIS to user \(n\), which also result in the closer outage performance under Rayleigh and Rician fading channels.

![Figure 6: Outage probability versus the transmit SNR, with \(K = 5\), \(\kappa = -5\) dB, \(\mathbb{E}\{|h_I|^2\} = -30\) dB, \(R_n = 0.1\) and \(R_m = 0.1\) BPCU.](图片占位符_Fig6)

As a further development, Fig. 6 plots the outage probability of STAR‑RIS‑NOMA networks versus SNR for the simulation with different pass loss expressions and \(\mathbb{E}\{|h_I|^2\} = -30\) dB. One can make the following observation from figure that with the decreasing of pass loss expression, the outage behaviors of user \(n\) and user \(m\) are becoming much worse in different communication environment. This is due to the fact that the pass loss expression is mainly determined by the propagation environment. When \(\alpha\) is relatively large, it indicates that there are many obstacles in the communication scenarios. This also confirms that the STAR‑RIS can be deployed to provide the LoS transmissions.

![Figure 7: Outage probability versus the transmit SNR, with \(K = 5\), \(\kappa = -5\) dB, \(\mathbb{E}\{|h_I|^2\} = -30\) dB, and \(R_n = R_m = 0.1, 0.5, 1.5\) BPCU.](图片占位符_Fig7)

In addition, Fig. 7 plots the outage probability of STAR‑RIS‑NOMA networks versus SNR with setting to be \(K = 5\), \(\kappa = -5\) dB, \(\mathbb{E}\{|h_I|^2\} = -30\) dB, and \(R_n = R_m = 0.1, 0.5, 1.5\) BPCU. It is observed that as the target rates increase, the larger outage probabilities are achieved for STAR‑RIS‑NOMA networks. The reason is that the achievable rates are directly combined with the target SNRs. It is favorable to decode the superposed signals for the user pairing selected with smaller target SNRs.

![Figure 8: Outage probability versus the transmit SNR and \(\tilde{a}\), with \(K = 5\), \(\kappa = -5\) dB and \(\mathbb{E}\{|h_I|^2\} = -30\) dB.](图片占位符_Fig8)

Fig. 8 plots the outage probability versus SNR and the dynamic power allocation factor \(\tilde{a} \in (0,1)\), with \(K = 5\), \(\kappa = -5\) dB, \(R_n = 0.5\) and \(R_m = 0.5\) BPCU. Let \(a_n = \tilde{a}\) and \(a_m = 1 - \tilde{a}\), which also satisfies the relationship with \(\tilde{a} < \frac{1}{\gamma_{thm} + 1}\). The analytical curves of outage probability of user \(n\) with pSIC and user \(m\) are plotted according to (15) and (18), respectively. One can observe that with the value of \(\tilde{a}\) increasing, the performance of user \(n\) with pSIC becomes better, while the outage behavior of user \(m\) deteriorates gradually. This is due to the fact that user \(m\) suffers from more interference when it detects its own information. Hence it is critical to seek out the optimal power allocation factors for balancing the performance of two users.

### B. Ergodic Rate

![Figure 9: Rate versus the transmit SNR, with \(K = 20\), \(\mathbb{E}\{|h_I|^2\} = -30\) dB, and \(\kappa = -5\) dB.](图片占位符_Fig9)

Fig. 9 plots the ergodic rates versus SNR, with \(K = 20\) and \(\kappa = -5\) dB. The right diamond and square solid curves for ergodic rates of user \(n\) with pSIC and user \(m\) for STAR‑RIS‑NOMA networks are plotted based on (30) and (33), respectively. Furthermore, the upper bound curve for ergodic rate of user \(n\) with pSIC is plotted based on (38), which can be better close to the theoretical expression. One can observe that the ergodic rate of user \(m\) converges to a throughput ceiling and thus obtain a zero high SNR slope, which is in line with the discussion in Remark 6. The right triangle solid curve for ergodic rate of user \(n\) with ipSIC is plotted according to (29) by invoking Matlab simulation software. Due to the influence of residual interference, the ergodic rate of user \(n\) with ipSIC tends to the constant value at high SNRs. In addition, we can see that the ergodic rate of user \(n\) with pSIC outperforms that of orthogonal users in the high SNR regime, while the ergodic rate of user \(m\) is inferior to that of orthogonal user. This is due to the fact the user \(n\) with pSIC gets a larger high SNR slope compared to orthogonal user. However, the high SNR slope of user \(m\) is equal to zero, which is less than orthogonal user.

![Figure 10: Rate versus the transmit SNR, with \(\kappa = -5\) dB and \(\mathbb{E}\{|h_I|^2\} = -30\) dB.](图片占位符_Fig10)

As a further advance, Fig. 10 plots the ergodic rates versus SNR for a simulation system with different reconfigurable elements. With increasing of reconfigurable elements, the ergodic rates of user \(n\) with pSIC for STAR‑RIS‑NOMA networks are becoming much larger relative to that of user \(m\).

### C. System Throughput

![Figure 11: System throughput in delay‑limited transmission mode versus SNR, with \(K = 5\) and \(\kappa = -5\) dB.](图片占位符_Fig11)

Fig. 11 plots the system throughput versus the transmit SNR for STAR‑RIS‑NOMA networks in the delay‑limited transmission mode, with \(K = 5\), \(\kappa = -5\) dB and \(R_n = R_m = 0.5\) BPCU. The system throughput curves of STAR‑RIS‑NOMA networks with ipSIC/pSIC is plotted according to (28). We can observe from the figure that the system throughput of STAR‑RIS‑NOMA with pSIC are superior to that of STAR‑RIS‑OMA at high SNRs. This is due to the fact that the system throughput in the delay‑limited transmission mode is affected by the outage probability. Due to the effect of residual interference, the system throughput of STAR‑RIS‑NOMA with ipSIC is worse than that of STAR‑RIS‑OMA. Hence it is important to consider the impact of ipSIC on STAR‑RIS‑NOMA network performance in practical scenarios. With the increasing of reflection elements, the STAR‑RIS‑NOMA networks are capable of providing the enhanced system throughput. This phenomenon can be explained as that the lower outage probability can be obtained by both the user \(n\) and user \(m\).

![Figure 12: System throughput in delay‑tolerant transmission mode versus SNR, with \(\mathbb{E}\{|h_I|^2\} = -30\) dB and \(\kappa = -5\) dB.](图片占位符_Fig12)

Furthermore, Fig. 12 plots the system throughput versus the transmit SNR for STAR‑RIS‑NOMA networks in the delay‑tolerant transmission mode, with \(K = 5\) and \(\kappa = -5\) dB. The system throughput of STAR‑RIS‑NOMA networks with ipSIC/pSIC based on (42). One can observe that the system throughput of STAR‑RIS‑NOMA networks with pSIC outperforms that of STAR‑RIS‑NOMA with ipSIC and STAR‑RIS‑OMA. As the number of reconfigurable elements increases, the START‑RIS‑NOMA networks is capable of achieving the enhanced system throughput.

---



# Secrecy Outage Probability Analysis for Downlink RIS-NOMA Networks With On-Off Control

In this section, numerical results are provided to substantiate the accuracy of theoretical expressions derived in the aforementioned sections for RIS‑NOMA networks. For sake of notational simplicity, Monte Carlo simulation parameters involved are summarized in Table I, where BPCU is an abbreviation for bit per channel use, and the number of Monte Carlo repetitions is \(10^6\) [7], [39] and \(a_{an}\) denotes the power allocation coefficient of AN. The path loss exponent \(\alpha\) is set to 2 and the trade‑off value of Gauss‑Laguerre integration parameter is 300. Suppose that \(K = 3\) and the variances of complex channel fading coefficients are represented as \(N_{br} = d_{br}^{-\alpha}\), \(N_{rk} = d_{rk}^{-\alpha}\) and \(N_{re} = d_{re}^{-\alpha}\), respectively. Without loss of the generality, the secure performance of RIS‑OMA and conventional OMA transmission schemes are considered as benchmarks. Specifically, time division multiple access is adopted for RIS‑OMA networks, where each user receives its own signal in one specific time slot and the entire process occupies a total of \(K\) orthogonal time slots. The AF relaying works in HD mode with a amplification factor of 2. The HD DF relaying equipped with a single antenna consumes two time slots to complete the communication, i.e., one for the BS‑DF relaying transmission and the other for the DF relaying‑users transmission, respectively. The FD DF relaying includes a pair of transceiver antennas [62]. In addition, the secrecy performance of AN‑aided NOMA networks is also taken into account, where the FD DF relaying will send AN based on a pseudo‑random sequence instead of RIS. Note that the sequence is known to the legitimate user, but remains unknown to the Eves [63], [64].

**TABLE I**  
THE TABLE OF MONTE CARLO SIMULATION PARAMETERS

| Parameter | Value |
|-----------|-------|
| Average SNR of Eve | \(\rho_e = 10\) dB |
| The power allocation coefficient for users | \(\{a_1,a_2,a_3\} = \{0.6,0.3,0.1\}\) |
| The power allocation coefficient for users with AN | \(\{a_1,a_2,a_3,a_{an}\} = \{0.4,0.2,0.1,0.3\}\) |
| The target secrecy rates for users | \(R_k^\phi = 0.04\) BPCU, \(k \in \{1,2,3\}, \phi \in \{EE,IE\}\) |
| The distance from BS to RIS | \(d_{br} = 3\) m |
| The distance from RIS to users | \(\{d_1,d_2,d_3\} = \{6\) m, \(4\) m, \(2\) m\(\}\) |
| The distance from RIS to Eve | \(d_{re} = 8\) m |

### A. External Eavesdropping Scenario

In this subsection, the secrecy outage behaviours of RIS‑NOMA networks is illustrated under external eavesdropping scenario.

![Figure 2: SOP versus transmitting SNR under external eavesdropping scenario, with \(M = 16\), \(P = 2\), \(Q = 8\), \(\rho_e = 0\) dB, \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(R_1^{EE} = R_2^{EE} = R_3^{EE} = 0.04\) and \(R_{OMA} = 0.12\) BPCU.](图片占位符_Fig2)

Fig. 2 plots the SOP versus transmitting SNR with the simulation setup \(M = 16\), \(P = 2\), \(Q = 8\) and \(R_1^{EE} = R_2^{EE} = R_3^{EE} = 0.04\) BPCU in external eavesdropping scenario. The analysis curves of SOP for LUs can be plotted according to (27) and (29), which are consistent with the simulation results. The accuracy of derivation is verified as the asymptotic curves realize convergence according to (34), (38) and (39). One can observe that the secrecy performance of the nearest LU \((k = 3)\) with pSIC is always superior to that of the distant LUs \((k = 1,2)\). The reason lies in that the near user obtains larger secrecy diversity order, which agrees with the conclusions in Remark 2. Another observation is that the SOP curves for users under ipSIC converges to an error floor at the high SNR and acquires a zero secrecy diversity order. This phenomenon can also be verified by the insights in Remark 1. In addition, we can see that the secrecy performance of RIS‑NOMA exceeds that of RIS‑OMA, AF relaying, HD/FD DF relaying and AN‑aided NOMA schemes. This can be understood as follows: 1) RIS‑NOMA has the ability to guarantee user fairness more effectively under multi‑user cases; 2) RIS‑NOMA operating in FD mode offers higher spectrum efficiency in comparison to HD/FD DF relaying; 3) RIS can provide superior security improvements for NOMA networks with lower energy consumption than confusing the Eves by asking the FD DF relaying to emit AN.

![Figure 3: SOP versus transmitting SNR for all LUs with different target secrecy rates under external eavesdropping scenarios, where \(M = 12\), \(P = 2\), \(Q = 6\), \(\rho_e = 10\) dB, \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -10\) dB.](图片占位符_Fig3)

Fig. 3 plots the SOP versus transmitting SNR for all LUs with different target secrecy rates under external eavesdropping scenarios, where \(M = 12\), \(P = 2\), \(Q = 6\) and \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -10\) dB. One can make the following observation from figure that with the increasing of target secrecy rate, the SOP of each LU rises monotonously, which is consistent with traditional NOMA networks. The reason behind this phenomenon is that the higher target security rates raise the threshold of SOP and partial secrecy capacity with small value will be considered as secrecy outage events.

![Figure 4: SOP versus transmitting SNR with varying reflecting elements under external eavesdropping scenarios, where \(M = Q\), \(P = 1\), \(\mathbb{E}\{|h_{ipu}|^2\} = -20\) dB, \(\rho_e = 10\) dB and \(R_1^{EE} = R_2^{EE} = R_3^{EE} = 0.04\) BPCU.](图片占位符_Fig4)

Fig. 4 plots system SOP versus transmitting SNR with various reflecting elements under external eavesdropping scenarios, where \(M = Q\), \(P = 1\), \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB and \(R_1^{EE} = R_2^{EE} = R_3^{EE} = 0.04\) BPCU. We can see from the figure that RIS‑NOMA is capable of achieving enhanced system SOP as the number of reflecting elements gradually grow from 4 to 20. This is because that passive beamformings can obtain a larger freedom of design space by applying more reflecting elements. Besides, the increased number of reflecting elements contribute to make the cascaded communication links more reliable and provide higher channel gains between BS and LUs.

![Figure 5: SOP versus transmitting SNR with various \(d_{br}\) and \(d_{rk}\) under external eavesdropping scenarios, where \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(\rho_e = 10\) dB, \(R_1^{EE} = R_2^{EE} = R_3^{EE} = 0.04\) BPCU, \(M = 12\), \(P = 2\) and \(Q = 6\). (a) Different \(d_{br}\). (b) Different \(d_{rk}\).](图片占位符_Fig5)

Fig. 5 plots the SOP versus transmitting SNR with various \(d_{br}\) and \(d_{rk}\) under external eavesdropping scenarios, where \(M = 12\), \(P = 2\), \(Q = 6\), \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB and \(R_1^{EE} = R_2^{EE} = R_3^{EE} = 0.04\) BPCU. As can be seen from Fig. 5(a), the security performance of LU is compromised since the distance between BS and RIS increases from \(3\) m to \(6\) m. This behavior is due to the fact that line of sight signals received at RIS become fuzzy due to the serious path fading as the RIS is deployed further away. Similarly, when \(d_{br}\) and \(d_{re}\) are both fixed while LUs depart from RIS, the line‑of‑sight signal is deteriorative and the SOP of users increases severely as indicated in Fig. 5(b). This is because that the Eve's eavesdropping ability remains unchanged and the superimposed message sent from RIS will suffer more path interference because of the larger transmission distance, which can heavily discount the quality of received signals.

![Figure 6: System SOP versus power allocation with fixed transmitting SNR under different eavesdropping scenarios, where \(\rho_e = 10\) dB, \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(R_1^{EE} = R_2^{EE} = 0.04\) BPCU, \(\phi \in \{EE,IE\}\), \(M = 16\), \(P = 2\) and \(Q = 8\). (a) External eavesdropping scenario. (b) Internal eavesdropping scenario.](图片占位符_Fig6)

Fig. 6(a) plots the system SOP versus power allocation with fixed transmitting SNR under external eavesdropping scenarios, where \(\rho = 10\) dB, \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(M = 16\), \(P = 2\), \(Q = 8\) and \(R_1^{EE} = R_2^{EE} = 0.04\) BPCU. Note that we consider a pair of users \((K = 2)\) in RIS‑NOMA networks while the power allocation coefficients for user 1 and user 2 are set as \(a_1 = a_T\) and \(a_2 = 1 - a_T\), where \(a_T\) presents the power offset parameter ranging from 0 to 1, i.e., \(a_T \in [0,1]\). One can observe from Fig. 6(a) that the system SOP is sensitive to the variation of power allocation for multiple users and providing the distant LU with a larger power allocation factor is beneficial to the secure performance of RIS‑NOMA networks. The reason is that NOMA specializes in allocating more power to the LUs distributed at the edge of cell to ensure they can receive high‑quality signals, which enhances the overall ability to resist wiretapping.

![Figure 7: Secrecy system throughput versus transmitting SNR for RIS‑NOMA, RIS‑OMA and conventional cooperative relaying, where \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(\rho_e = 10\) dB, \(M = Q = 16\), \(P = 1\) and \(R_1^{EE} = 0.08\), \(R_2^{EE} = 0.17\), \(R_3^{EE} = 0.25\) BPCU.](图片占位符_Fig7)

Fig. 7 plots the secrecy system throughput versus SNR in delay‑limited transmission mode under external eavesdropping case, where \(\rho_e = 10\) dB, \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(M = Q = 16\), \(P = 1\) and \(R_1^{EE} = 0.08\), \(R_2^{EE} = 0.17\), \(R_3^{EE} = 0.25\) BPCU. The black upper/lower triangular curves represent the secrecy system throughput with ipSIC/pSIC, which can be plotted based on (27) and (29), respectively. It is observed from the figure that the secrecy throughput of RIS‑NOMA is notably greater than that of RIS‑OMA, AF relaying, FD/HD relaying and AN‑aided NOMA schemes. The origin for this behavior can be explained that RIS‑NOMA networks has the advantages of high spectral efficiency and reliable channel environment. Another observation is that increasing the value of transmitting SNR, the throughput of various transmission schemes achieves the same convergency value. This is due to the fact that as SNR is on the verge of infinity, the SOPs of LUs become negligible and the secrecy system throughput is dominated by target secrecy rate.

### B. Internal Eavesdropping Scenario

![Figure 8: SOP versus transmitting SNR under internal eavesdropping scenario, with \(M = 16\), \(\rho_e = 10\) dB, \(R_1^{IE} = R_2^{IE} = R_3^{IE} = 0.04\) and \(R_{OMA} = 0.12\) BPCU.](图片占位符_Fig8)

Fig. 8 plots the SOP versus transmitting SNR in internal eavesdropping scenario, where \(M = 16\) and \(R_1^{IE} = R_2^{IE} = R_3^{IE} = 0.04\) BPCU. The analysis curves demonstrated can be acquired by (28) and (32). Additionally, asymptotes of SOP converge in the high SNR region based on (35), (42) and (43), which also confirms the correctness of derivation. It can be seen that the internal Eve can also compromise system security and error floors occur for LU 2 and LU 3, which is confirmed in Remark 3. This is owing to the detrimental influence caused by ipSIC where the previous information is not wiped out completely. Another observation is that LU 3 has a lower outage probability compared with LU 2. This is due to the fact that LU 3 is equipped with higher quality channel conditions, which gives it a greater advantage in anti‑eavesdropping. Furthermore, we can also observe that the secrecy outage behaviours of LUs are becoming worse since the setup of on‑off control varies from \(P = 2\), \(Q = 8\) to \(P = Q = 4\). The reason is that a smaller value of \(Q\) means fewer elements at RIS are set to 1 (on) for arbitrary \(\mathbf{v}_p\) and the channel gains for LUs are degraded because of the reduction of working elements.

![Figure 9: SOP versus transmitting SNR with different residual interference varies under internal eavesdropping case, where \(M = 12\), \(P = 2\), \(Q = 6\), \(\rho_e = 5\) dB, \(R_1^{IE} = R_2^{IE} = R_3^{IE} = 0.04\) and \(R_{OMA} = 0.12\) BPCU.](图片占位符_Fig9)

Fig. 9 plots the SOP versus transmitting SNR as the residual interference varies under internal eavesdropping case, where \(M = 12\), \(P = 2\), \(Q = 6\), \(R_1^{IE} = R_2^{IE} = R_3^{IE} = 0.04\) and \(R_{OMA} = 0.12\) BPCU. The simulation curves for ipSIC can be obtained from (28), while the curves presented for pSIC are generated based on (32). The asymptotic lines further verify the reliability of the derived results. It can be seen from the figure that the residual interference brought by ipSIC will impair the signal decoding process seriously. Moreover, with the increasing of residual interference, the achieved SOP of RIS‑NOMA will definitely converge to an inferior error floor. This can be explained that the high levels of ipSIC decrease the received SINR at LUs, which makes it fairly difficult for LUs to recover their own information. In consequence, it is essential to take into account the negative impact of ipSIC on network secure performance in actual communication cases.

Fig. 6(b) plots the system SOP versus power allocation with fixed transmitting SNR under internal eavesdropping scenarios, where \(\rho = 10\) dB, \(\mathbb{E}\{|h_{ipu}|^2\} = \mathbb{E}\{|h_{ipe}|^2\} = -20\) dB, \(M = 16\), \(P = 2\), \(Q = 8\) and \(R_1^{IE} = R_2^{IE} = 0.04\) BPCU. It can be seen from this figure that as the value of \(a_T\) increases, the secrecy outage behaviours of RIS‑NOMA networks become worse seriously, which is opposite to the observation in Fig. 6(a). The reason is that user 1 with poor channel conditions is regarded as an internal Eve, and allocating more power to user 1 can inevitably strengthen its eavesdropping ability while weakening the received signal quality of LUs, thus reducing the system SOP.

![Figure 10: Secrecy system throughput versus transmitting SNR for RIS‑NOMA under internal eavesdropping case, where \(\rho_e = 10\) dB and \(M = 16\).](图片占位符_Fig10)

Fig. 10 plots the secrecy system throughput versus SNR in delay‑limited transmission mode under internal eavesdropping case, where \(\rho_e = 10\) dB, \(M = 16\), \(P = 2\) and \(Q = 8\). The analysis curves of secrecy system throughput for RIS‑NOMA with ipSIC/pSIC are plotted according to (28) and (32), respectively. As can be observed from the figure, with the increase of residual interference, the secrecy system throughput of RIS‑NOMA is distinctly reduced under the circumstances of ipSIC. This is because that the deterioration of imperfect cancellation process will significantly weaken the received SINR at LUs and thus raise the SOP of users, which can directly impair the secrecy throughput performance referring to (45). Another observation is that the improvement of secrecy system throughput is achieved by increasing the target secrecy rate, while the secrecy outage behaviors are becoming worse when larger target secrecy rate is applied in RIS‑NOMA networks as illustrated in Fig. 3. Therefore, there exists a tradeoff to balance the performance of SOP and secrecy system throughput.

---



# A Unified NOMA Framework in Beam-Hopping Satellite Communication Systems

In this section, we focus on the numerical analysis of the proposed CD/PD‑NOMA‑BH systems. In Section V‑A, the satellite is designated to cover the equatorial ground region. The LEO coverage and users demand data are based on [39] and [51]. The satellite parameters and the number of beams refer to 3GPP TR 38.811 [52]. Note that the objective value \(\sum_{\phi \in (\mathcal{M}, \mathcal{N})}(R_{\phi} - D_{\phi})^2\) remains consistent with the minimal problem of the objective function in (7a). The number of simulation results exceeds 1000, where per user traffic demand is randomly distributed for each simulation. In Section V‑B, we utilize Monte Carlo simulation to discuss the results of performance analysis for the CD/PD‑NOMA‑BH systems. Moreover, BPCU is used to denote bit per channel use. In addition, the conventional OMA is regarded as a benchmark for comparison object. The parameter definitions are summarized in Table II unless stated otherwise.

**TABLE II**  
SIMULATION PARAMETERS

| Parameter | Value |
|-----------|-------|
| Frequency, \(f_{tr}\) | 11.7 GHz |
| Bandwidth, \(W\) | 200 MHz |
| Satellite covers the ground longitude range | \([85^\circ E, 115^\circ E]\) |
| Satellite covers the ground Latitude range | \([-15^\circ S, 15^\circ N]\) |
| Satellite location | \(101^\circ E\) |
| Satellite altitude | 1000 km |
| Power budget per user‑pair, \(P_s\) | 5 dBW |
| User receive antenna gain, \(G_r\) | 42.1 dBi |
| Satellite transmit antenna gain, \(G_t\) | 49.6 dBi |
| Number of time slots, \(T\) | 32 |
| Number of beams, \(B\) | 48 |
| Maximum active beams, \(B_0\) | 8.6 |
| Number of users per beam | 8 |
| Noise power, \(\sigma^2\) | \(-145\) dBW |
| Traffic demand, \(D_\phi\) | 200 Mb/s to 1.4 Gb/s |
| Minimum capacity, \(R_{\min}\) | 5 Mb/s |

### A. Simulation Results of Optimization

In this section, we compare U‑NOMA‑BH with three other BH algorithms as follows.

1) **Orthogonal multiple access beam hopping (OMA‑BH)**: The OMA‑BH scheme solves \(\mathcal{P}_0\) by Algorithm 2. Since there is no need for power and SC allocation, only (7b) and (7c) are considered, and a single user of the beam is analyzed.

2) **Maximum SINR beam hopping (Max‑SINR‑BH)**: The scheme divides the optimization function into subproblems in units of each time slot, and decides the allocation of time slots according to the users maximum SINR [53]. The Algorithm 1 is still used for optimization at user level.

3) **Periodic beam hopping (P‑BH)**: The scheme adopts round‑robin scheduling of beams [54]. Each beam is illuminated in turn with the same optimizations for SC and power.

![Figure 2: U‑NOMA‑BH scheme is compared with the benchmarks in terms of capacity gap.](图片占位符_Fig2)

Fig. 2 plots the performance comparison between the proposed U‑NOMA‑BH systems and the existing OMA‑BH, Max‑SINR‑BH, and P‑BH in the literature. As can be observed that the U‑NOMA‑BH systems outperform the other three benchmarks in controlling the difference between user achievable rate and traffic demand. When the average traffic demand is relatively small (less than \(450\) Mb/s), the performance gap between the OMA‑BH system and the proposed U‑NOMA‑BH systems is not widen. However, the difference multiples between U‑NOMA‑BH and OMA‑BH promoting from 0.03 to 0.34 when the demand increases from 450 to \(600\) Mb/s. This is because the systems of U‑NOMA‑BH optimize the SC and power in a single time slot. Compared to Max‑SINR‑BH and P‑BH, two BH algorithms, the U‑NOMA‑BH systems have obvious advantages, which also reduces the error of resource allocation caused by time slots allocation. In addition, the combination of the unified framework NOMA and BH can effectively improve the users satisfaction with resource allocation.

![Figure 3: Performance comparison of BCU and BEU based on different timeslots and number of active beams.](图片占位符_Fig3)

In addition, Fig. 3 plots the system of substituting the objective value with BCU and BEU, respectively, in different cases. To investigate the impact of U‑NOMA‑BH systems on user fairness, we transform the objective functions into \(\min_{\delta_{bt},\beta_{\phi k},a_{\phi t}}\sum_{m\in \mathcal{M}}(R_m - D_m)^2\) and \(\min_{\delta_{bt},\beta_{\phi k},a_{\phi t}}\sum_{n\in \mathcal{N}}(R_n - D_n)^2\). The performance metrics of BCU and BEU are analyzed by the impact of changes in the number of active beams and time slots, where \(T = 32\) or 64 and \(B_0 = 8\) or 6. We observe that changing the time slots and active beams number have an impact on the objective values for BEU at \(350\) Mb/s while BCU is at \(450\) Mb/s. At the same time, the fairness between BCU and BEU are improved by reducing the number of time slots and active beams. The phenomenon indicates that the achieved traffic demand is greater than the constraint objective value.

We take the case of introducing polarization as different benchmark schemes as follows.

1) **1c‑U‑NOMA‑BH**: The U‑NOMA‑BH systems are considered for full‑band reuse, and the users of active beams in each time slot share a frequency band.

2) **2c‑U‑NOMA‑BH**: The two‑color scheme introduces right‑and left‑hand side circular polarization, which can reduce the cochannel interference between active beams in the same time slot. The U‑NOMA‑BH adopts the two‑color scheme to reduce interbeams interference while ensuring that users have the full bandwidth of the satellite.

3) **4c‑U‑NOMA‑BH**: The four‑color scheme introduces frequency multiplexing on the basis of polarization multiplexing. The combination of the U‑NOMA‑BH and the four‑color scheme makes the interbeams interference smaller, but also pays the price of sacrificing the frequency band.

![Figure 4: Research of the achievable capacity of users with three different polarization reuse methods and users traffic requirements.](图片占位符_Fig4)

Fig. 4 compares the achievable capacity of the U‑NOMA‑BH systems introduced by polarization reuse. The bar graph reflects the comparison of U‑NOMA‑BH combined with the three polarization modes and the user traffic demand. Compared with other schemes, the 2c‑U‑NOMA‑BH can better fit the gap between the user achievable capacity and traffic demand. The reason for the phenomenon is that two‑color reuse not only reduces the interference between beams, but also enables users to achieve the full bandwidth, which fulfills the high‑traffic requirements of users. More particularly, in the 2c‑CD‑NOMA‑BH, the performance of users 1 and 7 is outstanding. It shows that the satisfaction of users is reached. The effects of users 4, 6, and 8 are almost a cliff‑like difference in the 4c‑PD‑NOMA‑BH. This shows that there are gaps between different polarization methods in achieving the satisfaction of users.

![Figure 5: Comparison of objective value performance of CD‑NOMA‑BH with different carrier conditions.](图片占位符_Fig5)

As a further advance, Fig. 5 plots the applicability of the proposed CD‑NOMA‑BH system for different scenarios. We can observe that if the transmit power is increased, the gap between the capacity and the traffic request becomes smaller, which is more suitable for user satisfaction. At the same time, it can be clearly seen from the figure that the SC allocation ratio \((K/Q)\) can significantly improve the performance of the CD‑NOMA‑BH system with different comparisons \((M, Q, K)\). In addition, the result shows that the performance of the CD‑NOMA‑BH system is superior as the number of assignable SC \(Q\) grows. This means that the additional intrabeam interference has less impact on the users achievable capacity, when the CD‑NOMA‑BH system can accommodate more active SC.

![Figure 6: Objective value versus the average traffic demand of users with ipCSI/CSI for the CD/PD‑NOMA‑BH systems.](图片占位符_Fig6)

Fig. 6 plots the applicability of the proposed CD/PD‑NOMA‑BH systems for different channel estimation errors. The red and blue lines represent CD‑NOMA‑BH and PD‑NOMA‑BH systems with ipCSI/pCSI, respectively, where \(\pi^* = 0.1\) and \(\pi^* = 0.2\) are postulated. We observe that the severe performance deteriorates as the channel estimation error increases. This is due to that ipCSI will lead to an overall addition in users interference and decrease the ability to satisfy traffic demands. Hence, it is crucial to consider the channel estimation error in practical scenarios for the U‑NOMA‑BH systems.

### B. Simulation Results of Performance Analysis

![Figure 7: Outage probability of the CD‑NOMA‑BH system versus SNR, with \(R_n = 1\) BPCU and \(R_m = 1.5\) BPCU.](图片占位符_Fig7)

Fig. 7 plots the outage probability versus SNR with different channel error and time slots overlap parameters for the CD‑NOMA‑BH system. Based on (23) and (25), the CD‑NOMA‑BH curves are plotted for different time slots overlap with respect to ipCSI, where \(\pi^* = 0.1\), \(\kappa = 0.2T\), and \(\kappa = 0.6T\) are set. The optimal power allocations \(a_n = 0.26\) and \(a_m = 0.74\) are given according to the optimization algorithm. Apparently, as the number of time slots overlaps increases, the interruption behavior of paired users becomes worse. This is due to the fact that the variable of time slots overlap mainly comes from the influence of interbeams interference. A larger amount of time slots overlap will lead to increase in the uncertainty of interbeams interference. For the purpose of comparison, the outage probability curve with pCSI, i.e., \(\pi^* = 0\), is adopted as the benchmark for comparison. It can be observed that the outage probability of users \(n\) and \(m\) decreases as \(\pi^*\) increases. As a consequence, the practical design of paired NOMA users within a beam should take into account the channel estimation error and the time slots overlap interbeams.

![Figure 8: Outage probability of the PD‑NOMA‑BH system versus SNR, with \(R_n = 1\) BPCU and \(R_m = 1.5\) BPCU.](图片占位符_Fig8)

Fig. 8 plots the effect of channel estimation error in the case of the PD‑NOMA‑BH system on the outage performance versus transmission SNR. For the special case of \(K = 1\), the outage probability curves of the BCU and BEU for the PD‑NOMA‑BH system are plotted according to (20), (21), (26), and (27). Furthermore, Monte Carlo simulation curves of BCU and BEU are plotted for ipCSI/pCSI with different amount of time slots overlap and coincide with the derived results. It can be observed that the outage probability of the PD‑NOMA‑BH system is higher than that of the CD‑NOMA‑BH. The reason for this phenomenon is that multiple SC can reduce interference within the beam.

![Figure 9: System throughput of the CD/PD‑NOMA‑BH systems versus SNR with ipCSI/pCSI.](图片占位符_Fig9)

Fig. 9 plots the effect of the considered channel error and time slots overlap on the system throughput. The red and blue lines represent the system throughput of CD‑NOMA‑BH and PD‑NOMA‑BH, respectively, which is obtained by (37) and (38). As can be observed that the system throughput of the CD‑NOMA‑BH is better than that of the PD‑NOMA‑BH. This is because that CD‑NOMA‑BH achieves the smaller outage probabilities. One can observed that the system throughput still decreases with increasing time slots overlap. The system throughput of ipCSI that we focus on is weaker than that of pCSI.

---



# Performance Analysis of Reconfigurable Intelligent Surface Assisted Two-Way NOMA Networks

In this section, the simulation results verify the rationality of the derived theoretical expressions for RIS‑TW‑NOMA networks. Table II is the parameter of the Monte Carlo simulation, where BPCU denotes the short for a bit per channel use. To verify the feasibility of the RIS‑TW‑NOMA networks, the outage probability, ergodic rate, energy efficiency, and system throughput are presented. Without loss of generality, the power allocation coefficients of a pair of users are selected as \(a_1 = 0.2\) and \(a_2 = 0.8\) respectively. More specifically, we show the impact of target rate, residual interference, and RIS elements on the performance of RIS‑TW‑NOMA networks. TWR‑OMA and RIS‑TW‑OMA is shown as the comparison benchmarks. Furthermore, the performance of the three transmission schemes is evaluated through computer simulation.

**TABLE II**  
THE PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^4\) iterations |
| Power allocation coefficients of NOMA | \(a_1 = 0.2\), \(a_2 = 0.8\) |
| Targeted data rates | \(R_1 = 2\) BPCU, \(R_2 = 5\) BPCU |

### A. Outage Probability

![Figure 2: Outage probability versus transmit \(P_u\) for TWR‑OMA, RIS‑TW‑OMA and RIS‑TW‑NOMA, with \(R_1 = 2\), \(R_2 = 5\) BPCU, \(\mathbb{E}\{|g_h|^2\} = -6\) dB and \(\mathbb{E}\{|\sigma_{I_1}|^2\} = -5\) dB.](图片占位符_Fig2)

Fig. 2 plots the outage probability of two users versus the transmit \(P_u\) for TWR‑OMA, RIS‑TW‑OMA, and RIS‑TW‑NOMA when \(M = 8\). The exact fork and diamond curve for outage probability of \(D_1\) with ipSIC/pSIC are plotted by (19) and (20), respectively. The exact right triangle curve for outage probability of \(D_2\) is plotted based on (22). The Monte Carlo simulation outage probability curves are relatively identical to analytical results across the entire SNR range, proving our theoretical derivation's correctness. One can observe that the outage probability with ipSIC converges to an error floor in the high SNR region and obtain a zero diversity order. This is due to the fact that the residual interference from ipSIC for RIS‑TW‑NOMA, which is also confirmed in Remark 1. The asymptotic curves for outage probability of \(D_1\) with ipSIC/pSIC and \(D_2\) are drawn according to (26), (27), and (28), respectively. As shown from the figure, the CLT‑based outage probability approximation curves are in accord with the exact outage probability curves in the low SNR region. The accuracy of the upper bounds for outage probability is higher than that of the CLT‑based outage probability approximations in the high SNR region. This is because that the skewed distribution of \(|h_m g_m|\) causes errors in the two curves. In the high SNR region, the CLT‑based outage probability approximations are inaccurate. Furthermore, the slopes of upper bounds for outage probability are the same as that of exact outage probability curves, which reveals that the upper bounds are accurate. The exact outage probability curves of RIS‑TW‑OMA are plotted according to the analytical results in (24). The critical observation is that the outage behaviors of RIS‑TW‑NOMA with pSIC are superior to that of TWR‑OMA and RIS‑TW‑OMA, particularly in the high SNR region. The reasons is that the RIS‑TW‑NOMA networks can realize much better user fairness than TWR‑OMA and RIS‑TW‑OMA networks for multiple users. Compared with the ipSIC scheme, the RIS‑TW‑NOMA networks with pSIC can achieve better outage behavior. As a result, it is important to consider the influence of ipSIC on the network performance for RIS‑TW‑NOMA in the practical scenario.

![Figure 3: Outage probability versus the transmit \(P_u\) with the different target rate.](图片占位符_Fig3)

Fig. 3 plots the outage probability of two users versus \(P_u\) with the different values of target rate for \(\mathbb{E}\{|g_h|^2\} = -6\) dB and \(\mathbb{E}\{|\sigma_{I_1}|^2\} = -5\) dB, and the values of target rate are reduced. One observation is that the different values of the target rate seriously affect the outage performance. As the values of the target rate decrease, the outage behaviors of users for RIS‑TW‑NOMA networks become better, followed by the users' behaviors in the conventional OMA networks.

![Figure 4: Outage probability versus the transmit \(P_u\) with the different residual interference.](图片占位符_Fig4)

Fig. 4 plots the outage probability of two users versus \(P_u\) with the different values of residual interference for \(R_1 = 2\), \(R_2 = 5\) BPCU, \(\mathbb{E}\{|\sigma_{I_i}|^2\} = -5\) dB and the values of residual interference are \(-10\) dB, \(-8\) dB and \(-5\) dB respectively. Each red curve corresponds to a residual interference value. The simulated red circle solid curves for outage probability of \(D_1\) with ipSIC are plotted according to (18), and the exact red fork solid curves for outage probability of \(D_1\) with ipSIC are plotted according to (19). It can be seen that the different values of residual interference affect the outage performance seriously. Due to the influence of residual interference from ipSIC, the outage probability of the nearby user with ipSIC converges to an error floor. As the values of residual interference increase, the outage behaviors of the \(D_1\) with ipSIC for RIS‑TW‑NOMA networks get worse and the preponderance of ipSIC is inexistent compared to pSIC. Therefore, it is imperative to consider the impact of ipSIC on the RIS‑TW‑NOMA network's performance in practical applications.

![Figure 5: Outage probability versus the transmit \(P_u\), with the different \(M\).](图片占位符_Fig5)

Fig. 5 plots the outage probability of users versus \(P_u\) for a simulation setting with \(R_1 = 2\), \(R_2 = 5\) BPCU, \(\mathbb{E}\{|g_h|^2\} = -6\) dB and \(\mathbb{E}\{|\sigma_{I_1}|^2\} = -5\) dB. The approximated outage probability curves for users match precisely with the simulation results. One can be observed that as the number of RIS elements increases, the RIS‑TW‑NOMA network is capable of achieving enhanced outage performance. The reason is that the application of RIS provides a new degree of freedom to enhance the wireless link performance. The conclusions also confirm this phenomenon in Remark 2, where the number of RIS elements influences outage probability for RIS‑TW‑NOMA.

![Figure 6: Outage probability versus \(P_u\) and \(a_\theta\) with \(M = 6\), \(R_1 = 2\) and \(R_2 = 5\) BPCU.](图片占位符_Fig6)

Fig. 6 plots the impact of the power allocation factor \(a_\theta\) as well as the transmit \(P_u\) on the performance of the outage probability in the RIS‑TW‑NOMA scheme, where \(a_\theta\) is dynamic power allocation coefficients, \(a_\theta \in [0,1]\). We fix a simulation setting with \(M = 5\), \(R_1 = 2\), \(R_2 = 5\) BPCU, \(\mathbb{E}\{|g_h|^2\} = -5\) dB, and \(\mathbb{E}\{|\sigma_{I_1}|^2\} = -6\) dB. Additionally, we assume that the power allocation coefficients of \(D_1\) and \(D_2\) have the relationships of \(a_1 = 1 - a_\theta\) and \(a_2 = a_\theta\). In this figure, it is illustrated that with the increase of the transmit \(P_u\), the power allocation factor \(a_\theta\) will be close to 1 when the maximum outage probability is achieved. In addition, the outage behavior of the nearby user becomes worse, and the performance of the distant user becomes better with the increase of the power allocation factor \(a_\theta\). This is due to the fact that \(D_1\) suffers more interference from \(D_2\).

![Figure 7: System throughput versus \(P_u\) in delay‑limited transmission mode.](图片占位符_Fig7)

Fig. 7 plots the curve of system throughput versus \(P_u\) in delay‑limited transmission mode. The graph is drawn according to (32), and \(M\) is set to 8. In this figure, the curves of system throughput with \(P_u\) in TWR‑OMA, RIS‑TW‑OMA and RIS‑TW‑NOMA schemes are drawn, respectively. As can be observed from the figure that the system throughput in RIS‑TW‑NOMA is better than that of RIS‑TW‑OMA in the low SNR region. In addition, by plotting the system throughput of the NOMA system without RIS‑aided under the same conditions, we can conclude that its performance in system throughput is inferior to the system with RIS assistance.

### B. Ergodic Rate

![Figure 8: Ergodic rate versus \(P_u\) with \(M = 8\), \(R_1 = 2\), \(R_2 = 5\) BPCU and \(\mathbb{E}\{|g_h|^2\} = -6\) dB.](图片占位符_Fig8)

Fig. 8 plots the ergodic rate of the user versus \(P_u\) for a simulation setting with \(R_1 = 2\), \(R_2 = 5\) BPCU, \(\mathbb{E}\{|g_h|^2\} = -5\) dB, and \(\mathbb{E}\{|g_{I_1}|^2\} = -6\) dB, which compares the ergodic rates of users in RIS‑TW‑OMA and RIS‑TW‑NOMA networks. These dots are the simulated values, and the lines are the theoretically derived values. In particular, the blue and black solid curves denote the ergodic rates of \(D_2\) and \(D_1\) with pSIC/ipSIC for RIS‑TW‑NOMA networks, which are plotted based on (34), (35), and (37), respectively. Moreover, the red curve represents the ergodic rates for RIS‑TW‑OMA networks drawn according to (39) and shown in the figure as a benchmark. One observation can be drawn that the ergodic rates for RIS‑TW‑NOMA are much greater than that of RIS‑TW‑OMA because RIS‑TW‑NOMA can realize much better user fairness. The ergodic rates of the nearby user with pSIC and the distant user are better than that of the nearby user with ipSIC. This reason is that the ergodic rate of the nearby user with ipSIC is affected by residual interference and an ergodic rate ceiling exists.

![Figure 9: Ergodic rate versus \(P_u\) with \(R_1 = 2\), \(R_2 = 5\) BPCU and the different \(M\).](图片占位符_Fig9)

Fig. 9 plots the ergodic rate of users versus \(P_u\) with the different number of reflecting elements of RIS for \(R_1 = 2\), \(R_2 = 5\) BPCU, \(\mathbb{E}\{|g_h|^2\} = -6\) dB and \(\mathbb{E}\{|g_{I_1}|^2\} = -5\) dB. These dots are the simulated values, and the lines are the theoretically derived values. One can observe that as the increase for the number of RIS elements, the RIS‑TW‑NOMA network is capable of achieving enhanced ergodic rate. Another observation is that the ergodic performance of the nearby user with pSIC has the same slopes with various numbers of RIS elements, which confirms the insights in Remark 5.

![Figure 10: System throughput versus \(P_u\) in delay‑tolerant transmission mode.](图片占位符_Fig10)

As a further advance, Fig. 10 plots the curve of system throughput versus \(P_u\) in delay‑tolerant transmission mode for TWR‑OMA, RIS‑TW‑OMA, and RIS‑TW‑NOMA. In this figure, the black and red solid curves represent the system throughput for RIS‑TW‑NOMA with ipSIC/pSIC, obtained from (43). The system throughput of TWR‑OMA and RIS‑TW‑OMA are selected to be the benchmarks denoted by the blue and red dash curves. It is observed that RIS‑TW‑NOMA can achieve higher throughput, and its tremendous value. This reason is that the RIS‑TW‑NOMA network can achieve an enhanced ergodic rate.

### C. Energy Efficiency

![Figure 11: Energy efficiency versus \(P_u\) in delay‑limited transmission mode.](图片占位符_Fig11)

Fig. 11 plots the curve of energy efficiency versus \(P_u\) in delay‑limited transmission mode for a simulation setting with \(P = 1\) dBw, \(\epsilon = 1.2\), \(P^{D_1} = P^{D_2} = 10\) dBm, the energy consumption \(P_{RIS}\) of RIS hardware is \(K P_k(b)\) and \(P_k(b) = 10\) dBm. The energy efficiency curves of RIS‑TW‑NOMA networks are plotted according to (45). It can be observed that RIS‑TW‑NOMA with ipSIC/pSIC has almost the same energy efficiency in the low SNR region. Nevertheless, the energy efficiency of RIS‑TW‑NOMA with pSIC is superior to ipSIC in the high SNR region. Another observation is that the energy efficiencies of RIS‑TW‑NOMA and RIS‑TW‑OMA networks are superior to that of TWR‑OMA networks. This is due to the RIS assisted wireless communications are capable of improving energy efficiency compared to these conventional cooperative communications.

![Figure 12: Energy efficiency versus \(P_u\) in delay‑tolerant transmission mode.](图片占位符_Fig12)

Fig. 12 plots the curve of energy efficiency for RIS‑TW‑NOMA in delay‑tolerant transmission mode for a simulation setting with \(P = 1\) dBw, \(\epsilon = 2\), \(P_1 = P_2 = 10\) dBm, the energy consumption \(P_{RIS}\) of RIS hardware is \(K P_k(b)\) and \(P_k(b) = 10\) dBm. The solid curves representing RIS‑TW‑NOMA with ipSIC/pSIC are obtained from (45), with throughput in delay‑tolerant mode. The dashed curves, representing energy efficiency for RIS‑TW‑OMA and TWR‑OMA. We can observe that the energy efficiency of RIS‑TW‑NOMA is much larger than that of RIS‑TW‑OMA and TWR‑OMA. This is due to that RIS‑TW‑NOMA can achieve the more significant system throughput relative to these benchmarks.

---



# Performance Analysis of Intelligent Reflecting Surface Assisted NOMA Networks

In this section, the numerical results are presented to confirm the rationality of the derived theoretical expressions for IRS‑NOMA networks. We show the impact of the reflecting elements on the performance of the IRS‑NOMA communication network. Monte Carlo simulation parameters used are summarized in Table II, where the pass loss exponent \(\alpha = 2\) aims to predigest simulation analysis and BPCU denotes the short for bit per channel use. Assume that three users \(M = 3\) are taken into consideration and the distance from the BS to IRS, and then to the terminal users are normalized to unity [12], [16], in which the unit of normalized distance for dimensionless physical quantity is generally taken as one. Different from the channel gains modeled using the 3GPP Urban Micro in [27], the variances of complex channel coefficients are set to be \(\Omega_{sr} = d_{sr}^{-\alpha}\), \(\Omega_{r1} = d_{r1}^{-\alpha}\), \(\Omega_{r2} = d_{r2}^{-\alpha}\) and \(\Omega_{r3} = d_{r3}^{-\alpha}\), respectively. The complexity‑vs‑accuracy tradeoff parameter is set to be \(N = 20\) and simulation results are denoted by \(\bullet\). Without loss of the generality, the IRS‑OMA and conventional OMA (i.e., variable gain AF relaying, FD/HD DF relaying) are selected as the benchmarks for the purpose of comparison. Here AF relaying works in HD mode and is equipped with a single antenna. The FD DF relaying is equipped with a pair of transceiver antennas, while HD DF relaying has a single antenna. The target rate \(R_{oma}\) of the orthogonal user is equal to \(\sum_{i = 1}^{M} R_i\).

**TABLE II**  
THE PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Power allocation coefficients of NOMA | \(\{a_1, a_2, a_3\} = \{0.1, 0.3, 0.6\}\) |
| Rician factor | \(\kappa\) |
| Target rates for IRS‑NOMA users | \(R_1 = 0.6\) BPCU, \(R_2 = 1.6\) BPCU, \(R_3 = 2\) BPCU |
| IRS‑OMA target rate | \(R_{oma} = \sum_{i=1}^M R_i\) |
| Distances from IRS to users | \(d_{r1} = 0.5\), \(d_{r2} = 1.0\), \(d_{r3} = 1.5\) |

### A. Outage Probability

![Figure 2: Outage probability versus the transmit SNR, with \(K = 1\), \(Q = 1\), \(P = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\), \(R_3 = 2\) and \(R_{oma} = 4.2\) BPCU.](图片占位符_Fig2)

Fig. 2 plots the outage probability of three users versus SNR for a simulation setting with \(K = 1\), \(Q = 1\), \(P = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\), \(R_3 = 2\) and \(R_{oma} = 4.2\) BPCU. The theoretical analysis curves of outage probability for users with pSIC are plotted according to (10). It is obvious that the Monte Carlo simulation outage probability curves excellently agree with analytical results across the entire average SNR range. The asymptotic outage probability converges to the analytical expressions given in (16), which proves the effectiveness of our theoretical derivation. As can be seen from the figure that the outage performance of the nearest user \((M = 3)\) is higher than that of the distant users \((m = 2\) and \(m = 1)\). This is due to the fact that the nearby user attains the higher diversity order, which verifies the insights in Remark 2. The exact and asymptotic outage probability curves of IRS‑OMA are plotted according to the analytical results in (12) and (19), respectively. One can observe that the outage behaviors of IRS‑NOMA with pSIC are superior than that of IRS‑OMA (12), variable gain AF relaying [54], FD DF relaying with imperfect loop self‑interference cancellation, i.e., \(\mathbb{E}\{|h_L|^2\} = -10\) dB [55, Eq. (7)], FD DF relaying with perfect loop self‑interference cancellation and HD relaying [55, Eq. (8)]. The reasons are that: 1) IRS‑NOMA can realize much better user fairness than IRS‑OMA for multiple users; 2) FD DF relaying with imperfect loop self‑interference cancellation suffers from loop interference due to signal leakage and needs the advanced loop interference cancellation technologies, which will lead to the higher cost; and 3) IRS‑NOMA operates in FD mode provides the more spectrum efficient than HD DF relaying and FD DF relaying with perfect loop self‑interference cancellation.

![Figure 3: Outage probability versus the transmit SNR with different residual interference.](图片占位符_Fig3)

Fig. 3 plots the outage probability of three users versus SNR for a simulation setting with \(K = 2\), \(Q = 2\), \(P = 1\), \(\varpi = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\), \(R_3 = 2\) and \(R_{oma} = 4.2\) BPCU. The exact and approximate analyses curves of outage probability for users with ipSIC are plotted by (9) and (14), respectively. The exact and asymptotic outage probability curves of IRS‑OMA are plotted by (12) and (20), respectively. The simulation results matches closely with the theoretical analysis. The important observation is that the outage probability of distant users with ipSIC converges to an error floor in the high SNR regime and thus obtain a zero diversity order. The reason is that there is the residual interference from ipSIC for IRS‑NOMA. This phenomenon is also confirmed by the conclusions in Remark 1. Additionally, it is worth noting that the farthest user \((m = 1)\) does not carry out the SIC operation, since it has the worst channel conditions. Compared to the benchmark of IRS‑OMA, we observe that IRS‑NOMA with ipSIC is also capable of achieving the lower outage behaviors. Certainly, with the value of residual interference increasing, the achieved outage probability of IRS‑NOMA converges to the worst error floors. As a result, it is important to consider the influence of ipSIC on the network performance for IRS‑NOMA in the practical scenario.

![Figure 4: Outage probability versus the transmit SNR, with \(P = 1\), \(\varpi = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\), \(R_3 = 2\) BPCU and \(\mathbb{E}\{|h_I|^2\} = -10\) dB.](图片占位符_Fig4)

Fig. 4 plots the outage probability versus SNR for a simulation system with different reflecting elements of IRS and \(\mathbb{E}\{|h_L|^2\} = -10\) dB. One can observe that the setting of the reflecting elements for IRS‑NOMA is significant to provide the network performance. With increasing the number of reflecting elements \(K\), the lower outage probabilities are attained for multiple users. These behaviors are caused by the fact that the application of IRS to NOMA networks provides a new degree of freedom to enhance the wireless link performance. This phenomenon is also certificate the completion of Remark 2, where both the number of reflecting elements and channel ordering determine the slope of outage probability for IRS‑NOMA. Another observation is that all outage probability curves of each user have the same slopes, which manifests that the diversity orders of users are the same. This appearance demonstrates the insight we derived from the analytical results given by (16).

![Figure 5: Outage probability versus the transmit SNR, with \(\varpi = 1\), \(Q = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\), \(R_3 = 2\) BPCU and \(\mathbb{E}\{|h_I|^2\} = -10\) dB.](图片占位符_Fig5)

Fig. 5 plots the outage probability versus SNR for a simulation setting with \(Q = 1\), \(\varpi = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\), \(R_3 = 2\) BPCU and \(\mathbb{E}\{|h_I|^2\} = -10\) dB. The approximated outage probability curves of users are plotted corresponding to (15), which match precisely with the simulation results. As can be observed from the figure that as the number of reflecting elements increases, the outage probability of users is becoming much smaller. The main reason behind this is that IRS‑NOMA with 1‑bit coding provides much more diversity orders given by Remark 2. It is worth mentioning that the outage probability curves of each user has a different diversity order, which confirms the analytical result derived in (15).

![Figure 6: Outage probability versus the transmit SNR, with the different target rate for \(K = 2\), \(P = 2\) and \(Q = 1\).](图片占位符_Fig6)

Fig. 6 plots the outage probability versus SNR with the different target rate for \(K = 2\), \(P = 2\) and \(Q = 1\). One can observe that adjusting the target rate of users largely affect the outage performance. With the values of target rate increasing, the outage behaviors of users for IRS‑NOMA networks are becoming much worse, which is in line with the conventional NOMA networks [7].

![Figure 7: Outage probability versus distance \(d_{sr}\) between the BS and IRS, with \(Q = 2\), \(K = 2\), \(P = 1\), \(R_1 = R_2 = R_3 = 0.6\) BPCU, \(R_{oma} = 1.8\) BPCU.](图片占位符_Fig7)

Fig. 7 plots the outage probability as a function of the normalized distance between the BS and users, with \(Q = 2\), \(K = 2\), \(P = 1\), \(R_1 = R_2 = R_3 = 0.6\) BPCU, \(R_{oma} = 1.8\) BPCU. We can observe that when the IRS is deployed closely to BS, the outage performance of non‑orthogonal users is becoming much better. This phenomenon can be explained that the IRS can receive the clear LoS signals from the BS for the purpose of maximizing its received signal power. As the IRS departs from BS, the LoS deteriorates and outage probability of users increases seriously. When the IRS is in the middle of the BS and users, the worst outage behaviors of users are attained in IRS‑NOMA networks. This is due to the fact that the IRS is neither closed to the BS nor to users. After this point, the performance begins to improve again. This is because that the IRS is close to NOMA users and enhance the reflecting signals received by users, which is consistent with the conclusion in [56]. Such an outage behavior can be useful to establish an optimal deployment of IRS in NOMA networks. Consequently, the deployment scenarios of IRS should take into account some practical constraints.

![Figure 8: Outage probability versus the transmit SNR and \(a_\theta\) with \(K = 1\), \(P = 1\), \(Q = 1\), \(R_1 = 0.1\) and \(R_2 = 0.4\) BPCU.](图片占位符_Fig8)

To illustrate the impact of fixed power allocation coefficients on system performance, Fig. 8 plots the outage probability versus SNR and \(a_\theta\), with \(K = 1\), \(P = 1\), \(Q = 1\), \(R_1 = 0.1\) and \(R_2 = 0.4\) BPCU, where \(a_\theta\) is dynamic power allocation coefficients and the value range is zero to one, i.e., \(a_\theta \in [0,1]\). We assume that there are a pair of users \((M = 2)\) in IRS‑NOMA networks and the power coefficients of user 1 and user 2 have the relationships of \(a_1 = 1 - a_\theta\) and \(a_2 = a_\theta\). The analytical curves of outage probability are plotted according to (10). It is observed from the figure that with the value of \(a_\theta\) increasing, the outage behavior of user 1 deteriorates gradually, while the performance of user 2 first becomes better and then tends to worse. The reason for this phenomenon is that user 1 suffers more interference from user 2 when it detects its own information. At this time, user 2 needs to detect the signal of user 1 before detecting its own signal. Hence it is critical to design the power allocation coefficients for balancing the performance of two users.

![Figure 9: Outage probability versus SNR over Rician fading channels.](图片占位符_Fig9)

Fig. 9 plots the outage probability versus SNR over Rician fading channels, with \(K = 1\), \(R_1 = 0.6\), \(R_2 = 1.6\) and \(R_3 = 2\) BPCU. The Rician fading channel is a frequently used model, where the LoS path is large and has a known magnitude, and that there are also a large number of independent paths. As can be seen from the figure that with the increase of Rician factor value, i.e., from \(\kappa = -40\) dB to \(\kappa = -10\) dB, the outage probability of non‑orthogonal users with pSIC for IRS‑NOMA networks is becoming much better compared to Rayleigh fading channels. The basic reason for this behavior is that the more signal components from LoS paths arrive at the receiving node and enhance the outage performance of NOMA‑IRS networks.

### B. Ergodic Rate

![Figure 10: Rates versus the transmit SNR, with \(K = 1\), \(Q = 1\) and \(P = 1\).](图片占位符_Fig10)

Fig. 10 plots the ergodic rates versus SNR, with \(K = 1\), \(Q = 1\) and \(P = 1\). The red and blue dotted curves denote the ergodic rates of the \(m\)-th user \((m = 2)\) and \(M\)-th user \((M = 3)\) with ipSIC for IRS‑NOMA networks, which are plotted according to (22) and (23), respectively. The exact curves of ergodic rate for the \(m\)-th and \(M\)-th user with pSIC are plotted based on (24) and (25), respectively. One can observe that the ergodic rates of the \(m\)-th and \(M\)-th user with ipSIC are inferior to that of the \(m\)-th and \(M\)-th user with pSIC. The main reason is that the ergodic rates suffer from the residual interference of ipSIC and tends to constant values at high SNRs. Another observation is that the ergodic rates of distant users for IRS‑NOMA outperform that of AF relaying and FD/HD relaying in the low SNR regime, which are consistent to FD/HD NOMA systems [10], [12]. As the SNR value increases, the ergodic rate of distant users converges to a throughput ceiling, which is also confirmed in Remark 4. This is due to the fact that the distant user will suffer from the interference from the nearby users' signals when it decodes their own signals. Another observation is that the ergodic rate of nearest user is much greater than that of non‑orthogonal users, IRS‑OMA (27), AF relaying and FD/HD relaying. The origin for this behavior is that it is closest to the IRS and has the best channel conditions.

![Figure 11: Rates versus the transmit SNR, with \(Q = 1\).](图片占位符_Fig11)

In addition, Fig. 11 plots the ergodic rates versus SNR with different reflecting elements. As can be observed from this figure that with the increasing reflecting elements of IRS, the ergodic performance of the nearest user with pSIC is enhanced and has the same slopes, which confirms the insights in Remark 5. The distant users' performance has no obvious variety due to the effects of interference signals. We conclude that IRS‑NOMA cannot circumvent the problem of zero slope for the distant users.

### C. Energy Efficiency

![Figure 12: Energy efficiency in delay‑limited transmission mode, where \(K = 2\), \(Q = 2\), \(P = 1\), \(\kappa = 1.2\), \(P_S = 5\) dBw, \(P_{BS} = 2\) dBw, \(P_{m,UE} = 10\) dBm and \(P_k(b) = 10\) dBm.](图片占位符_Fig12)

Fig. 12 plots the energy efficiency for IRS‑NOMA networks in the delay‑limited transmission mode, with \(K = 2\), \(Q = 2\), \(P = 1\), \(\kappa = 1.2\), \(P_S = 5\) dBW, \(P_{BS} = 2\) dBW, \(P_{m,UE} = 10\) dBm and \(P_k(b) = 10\) dBm. The energy efficiency curve of IRS‑NOMA networks with ipSIC/pSIC is plotted according to (34). It can be observed that the energy efficiency of IRS‑NOMA outperforms that of IRS‑OMA and converge to the same value in the high SNR regime. This is due to the fact that the setting of sum target rate for non‑orthogonal users is equal to the orthogonal user in delay‑limited transmission mode. Another observation is that the energy efficiencies of IRS‑NOMA and IRS‑OMA are superior to that of AF relaying and FD/HD DF relaying. The main reason is that the IRS‑assisted wireless communications are capable of improving the energy efficiency compared to these conventional cooperative communications.

![Figure 13: Energy efficiency in delay‑tolerant transmission mode, where \(K = 2\), \(Q = 2\), \(P = 1\), \(\kappa = 1.5\), \(P_S = 10\) dBw, \(P_{BS} = 4\) dBw, \(P_{m,UE} = 10\) dBm and \(P_k(b) = 10\) dBm.](图片占位符_Fig13)

As a further advance, Fig. 13 plots the energy efficiency for IRS‑NOMA in delay‑tolerant transmission mode, with \(K = 2\), \(Q = 2\), \(P = 1\), \(\kappa = 1.5\), \(P_S = 10\) dBW, \(P_{BS} = 4\) dBW, \(P_{m,UE} = 10\) dBm and \(P_k(b) = 10\) dBm. The energy efficiency curve of IRS‑NOMA networks with pSIC is plotted according to (34). We can observe that the energy efficiency of IRS‑NOMA is much larger than that of IRS‑OMA, AF relaying, FD/HD DF relaying. This is due to that IRS‑NOMA with pSIC is able to achieve the larger system throughput relative to these benchmarks.

---



# Secure Communications in a Unified Non-Orthogonal Multiple Access Framework

In this section, the numerical results of secrecy transmission for unified NOMA framework are present to verify the accuracy of the analytical expressions, where both external and internal eavesdropping scenarios are discussed in detail. We show interplay of different system configuration parameters and impacts on the SOP for CD/PD‑NOMA networks. Monte Carlo simulation parameters used in this section are summarized in Table I [44], [45], where BPCU is abbreviation of bit per channel use. Simulation results are denoted by \(\bullet\) and the complexity‑vs‑accuracy tradeoff parameters are set to be \(U = 15\) and \(W = 160\). In external eavesdropping scenario, the conventional OMA scheme is selected to be a benchmark for comparing the secrecy performance of unified NOMA framework, while the security performance of PD‑NOMA is viewed as baseline for the purpose of comparison in internal eavesdropping scenario.

**TABLE I**  
TABLE OF PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^5\) iterations |
| Carrier frequency | 1 GHz |
| The radius of a disc region for Eves | 1000 m |
| Path loss exponent | \(\alpha = 2\) |
| Power allocation coefficients of NOMA | \(a_m = 0.8, a_n = 0.2\) |
| Targeted data rates | \(R_n = R_m = 0.01\) BPCU |
| The radius of the \(n\)-th LU zone | \(R_{D_1} = 2\) m |
| The radius of the \(m\)-th LU zone | \(R_{D_2} = 10\) m |

### A. External Eavesdropping Scenario

In this subsection, the secrecy performance of CD/PD‑NOMA networks is characterized in terms of SOP for external eavesdropping scenario.

![Figure 2: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(R_n = R_m = 0.01\) BPCU.](图片占位符_Fig2)

Fig. 2 plots the SOP versus \(\rho\) with different residual interference values, where \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(R_n = R_m = 0.01\) BPCU. The exact analytical curves of SOP for the \(n\)-th user with ipSIC and pSIC are plotted based on (18) and (19), respectively. The exact theoretical curve of SOP for the \(m\)-th user is plotted based on (23). It can be seen that the numerical evaluation curves match with analytical results. The exact asymptotic curves of SOP for the \(n\)-th user with ipSIC and pSIC are plotted based on (33) and (35), respectively. The exact asymptotic curve of SOP for the \(m\)-th user is plotted based on (38). Moreover, the approximate analysis results of SOP perfectly match with the theoretical analysis in the high SNR region. One can observe that the secrecy outage behavior of the \(n\)-th user with pSIC is superior to that of the OMA scheme, while the security performance of the \(m\)-th user is inferior to OMA. This comes from the fact that NOMA scheme is capable of providing more user fairness in comparison to OMA [9], [14], [15]. Another significant observation is that SOP of the \(n\)-th user with ipSIC converge to an error floor and thus gain a zero secrecy diversity order. The reason is that the ipSIC scheme employed at \(n\)-th user for the main channel brings the effect of residual interference on outage probability, which verifies the conclusion in Remark 1. In the case of fixed the residual interference level, i.e., \(\varpi = 1\), as the residual interference value from \(-30\) dB to \(-20\) dB increases, the outage performance of the \(n\)-th user with ipSIC is becoming more worse. That is to say that the corresponding error floors for SOP are becoming more larger. Furthermore, the different impact levels of residual interference also degrade the secrecy performance seriously. More specifically, under the condition of \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = \mathbb{E}\{\|\mathbf{h}_{I_e}\|_2^2\} = -30\) dB, with the value of \(\varpi\) increasing from \(\varpi = 0.3\) to \(\varpi = 1\), the superiority of outage behaviors for the \(n\)-th user with ipSIC is no longer obvious. These imply how to eliminate the residual interference should be taken into account in practical secrecy NOMA scenarios.

![Figure 3: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(\alpha = 2\), \(\varpi = 1\) and \(R_n = R_m = 0.01\) BPCU.](图片占位符_Fig3)

Fig. 3 plots the SOP versus \(\rho\) with different subcarriers \(K\), \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(\alpha = 2\), \(\varpi = 1\) and \(R_n = R_m = 0.01\) BPCU. As can be seen from this figure, with the number of subcarriers increasing, the slopes of SOP for CD‑NOMA (\(K = 3\)) are larger than that of PD‑NOMA (\(K = 1\)). This can be explained by the fact that the secrecy CD‑NOMA network provides a diversity gain that is equal to the number of subcarriers \(K\), which is also validated by the insights in Remark 3 and Remark 4. This implies that by spreading the user's information into a plurality of subcarriers, CD‑NOMA has enhanced the secrecy performance of users achieved and provided spread spectrum gain with respect to PD‑NOMA.

![Figure 4: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(\varpi = 1\).](图片占位符_Fig4)

Fig. 4 plots the SOP versus \(\rho\) with different target secrecy rates, where \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(\varpi = 1\). One can show that the selection of target secrecy rate has a greater impact on the SOP for NOMA networks. With increasing of the target secrecy rates, the outage probability of users for secrecy NOMA are becoming worse seriously. It is worth pointing out that the adaptive secrecy target rates has a large effect on the performance of secure communication for CD/PD‑NOMA networks. As a consequence, the requirements of smaller secrecy rate can be applied into small packet business and internet of things scenarios.

![Figure 5: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\) and \(\varpi = 1\).](图片占位符_Fig5)

Fig. 5 plots the SOP versus \(\rho\) with different path loss exponents \(\alpha = 2,3,4\), where \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\) and \(\varpi = 1\). It can be seen from this figure that by increasing the path loss exponent, i.e., more severe path loss, leads to a poorer secrecy outage behaviors. It is worth mentioning that the effect of path loss on the secrecy performance of the \(n\)-th user is smaller, while has a greater impact on the \(m\)-th user. The main reason for this result is that the \(m\)-th user is far away from BS and is greatly affected by large‑scale fading.

![Figure 6: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(\varpi = 1\).](图片占位符_Fig6)

Furthermore, the SOP versus the transmit SNR with different radius distance is plotted in Fig. 6. It is observed that the better SOP can be achieved by reducing the radius of user distance, since the smaller radius distance results in a lower path loss.

![Figure 7: The SOP versus \(\rho\) with \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(R_n = R_m = 0.01\) BPCU.](图片占位符_Fig7)

To observe how the transmit SNR affects the secrecy outage behaviors in the unified NOMA framework, we present the curves of SOP versus \(\rho\) and \(\rho_e\) in Fig. 7, where \(\lambda_e = 10^{-3}\), \(K = 2\), \(\alpha = 2\) and \(R_n = R_m = 0.01\) BPCU. As can observed from the figure, with the increase of \(\rho_e\), the SOP of the \(n\)-th and \(m\)-th user is gradually reduced on the condition of pSIC, while the SOP of the \(n\)-th user with ipSIC converges to a constant value. The main reason can be explained as that the channels of Eves are evolving by increasing \(\rho_e\) which will lead to the inferior secrecy performance. Another reason is that the imperfect cancellation scheme employed brings more residual interference. Fixing the SNR, i.e., \(\rho_e = 20\) dB, when \(\rho\) increases, the SOP of the \(n\)-th user and \(m\)-th user is becoming smaller. This is due to that the channels of the Eves are degrading with the increasing of the transmitted power of the BS. As a consequence, it is important to consider the impact of channels of Eves on the secrecy performance in practical PLS scenarios.

### B. Internal Eavesdropping Scenario

In this subsection, the secrecy outage behaviors of the \(m\)-th user to wiretap the \(n\)-th user are evaluated for CD/PD‑NOMA.

![Figure 8: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\) and \(R_{D_1} = 2\) m.](图片占位符_Fig8)

Fig. 8 plots the SOP versus \(\rho\) where \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\) and \(R_{D_1} = 2\) m. Under the conditions of ipSIC/pSIC, the exact SOP curves of the \(m\)-th user to wiretap the \(n\)-th user for CD‑NOMA and PD‑NOMA are plotted based on (28), (29) and (30), (31), respectively. The analytical results are consistent with simulation results, which further confirm the accuracy of derived results. As can be observed from this figure that the secrecy outage behaviors of the \(m\)-th user to wiretap the \(n\)-th user for CD‑NOMA outperform that of the \(m\)-th user to wiretap the \(n\)-th user for PD‑NOMA. This is because that CD‑NOMA is capable of obtaining more diversity gain. Another observation is that the residual interference levels of ipSIC have a greater impact on secrecy behaviors. As \(\varpi\) becomes small from \(\varpi = 1\) to \(\varpi = 0.5\), the performance gain brought by ipSIC is becoming more obvious. Additionally, increasing the value of residual interference with the fixed interference level, i.e., \(\varpi = 1\), the secrecy behaviors of internal eavesdropping scenario are becoming worse. Hence it is important to predominate the influence of residual interference when performing physical layer secure communication.

![Figure 9: The SOP versus \(\rho\) with \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\) and \(\varpi = 1\).](图片占位符_Fig9)

Fig. 9 plots the SOP versus \(\rho\) with different distances, where \(\rho_e = 10\) dB, \(\lambda_e = 10^{-3}\), \(K = 2\), \(\varpi = 1\) and \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -30\) dB. It can be obviously seen from the figure that the theoretical and simulation results are closely matched for different parameters. As observed from figure that increasing the distance between BS and users will reduce the SOP, which can be explained as the secrecy behaviors of the \(m\)-th user to wiretap the \(n\)-th user are progressively affected by the large scale fading.

From the perspective of numerical results in the above figures, when the transmitting power of BS is changed, the received SNR of Eves is considered to be fixed and equal to 10 dB for both external and internal scenarios. To clarify how would it be possible to degrade the channel of Eves without affecting the channel of the LUs, we assume that \(\rho_e\) is proportional to \(\rho\), i.e., \(\rho_e = \beta \rho\), where \(\beta\) is a positive scaling factor. As can be observed from Fig. 10 and Fig. 11 that the secrecy behaviors of LUs is becoming progressively worse as \(\beta\) increases (i.e., \(\beta = 0.1, 0.5\) and 1). This is due to the fact that the greater \(\beta\) means a higher transmit power of Eves, which in turn increases the interference at LUs. In addition, the channels of Eves might be degraded by utilizing some approaches such as broadcasting noise by the BS or relays and we will take these into considered in our future work.

![Figure 10: For different \(\beta\) in external eavesdropping scenario, with \(\rho_e = \beta \rho\), \(\lambda_e = 10^{-3}\), \(K = 2\) and \(\varpi = 1\).](图片占位符_Fig10)

![Figure 11: For different \(\beta\) in internal eavesdropping scenario, with \(\rho_e = \beta \rho\), \(\lambda_e = 10^{-3}\), \(K = 2\) and \(\varpi = 1\).](图片占位符_Fig11)

---



# Outage Behaviors of NOMA-Based Satellite Network Over Shadowed-Rician Fading Channels

In this section, the numerical results are provided and show the impact of system parameters on NOMA‑based satellite communication network. The links between satellite and terrestrial users are subject to Shadowed‑Rician fading with channel parameters given in Table I [18]. Monte Carlo simulation parameters used in this section are summarized in Table II [22]. We assume that there are three users in the network, i.e., \(M = 3\). The power allocation factors for multiple users are set to be \(a_1 = 0.5\), \(a_2 = 0.4\), \(a_3 = 0.1\), respectively. Without loss of generality, the conventional OMA is selected to be a baseline, where the target rate \(R_o\) of orthogonal user is equal to the sum rate of non‑orthogonal users, \(R_1 = 0.1\), \(R_2 = 0.5\) and \(R_3 = 1\) bit per channel use.

**TABLE I**  
TABLE OF PARAMETERS FOR SATELLITE COMMUNICATIONS CHANNEL

| Shadowing | \(b\) | \(m\) | \(\Omega\) |
|-----------|------|------|---------|
| Frequent heavy shadowing (FHS) | 0.063 | 0.739 | \(8.97 \times 10^{-4}\) |
| Average shadowing (AS) | 0.126 | 10.1 | 0.835 |
| Infrequent light shadowing (ILS) | 0.158 | 19.4 | 1.29 |

**TABLE II**  
TABLE OF PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^5\) iterations |
| Satellite orbit type | LEO |
| Carrier frequency | 1 GHz |
| 3dB angle \(\phi_{3\mathrm{dB}}\) | \(0.4^\circ\) |
| User's antenna gain per beam | 3.5 dBi |
| Satellite's antenna gain per beam | 24.3 dBi |
| The distance between satellite and users | 1000 km |
| The angle between the beam center and users | \(0.1^\circ\) |

![Figure 1: Outage probability versus the transmit SNR.](图片占位符_Fig1)

Fig. 1 plots the outage probability versus the transmit SNR with satellite channel experiencing FHS. The exact outage probability of curves for the \(p\)-th terrestrial user (i.e., \(p=1\), \(p=2\) and \(p=3\)) with ipSIC/pSIC are given by numerical simulations and perfectly match with the analytical expressions. The asymptotic curves well approximate the exact outage probability curves. Due to the influence of residual interference, the outage probability of terrestrial users with ipSIC converge to an error floor. With increasing the value of residual interference, the outage behaviors of terrestrial user \((p=2)\) with ipSIC are getting worse compared to other users. Another observation is that the outage performance of non‑orthogonal users with pSIC is superior to that of orthogonal user. The basic reason for this phenomenon is that NOMA is capable of providing much more fairness when it serves multiple users at the same time [2].

![Figure 2: Outage probability versus the transmit SNR.](图片占位符_Fig2)

Fig. 2 plots the outage probability versus the transmit SNR with different satellite channel parameters for the simulation setting \(\phi_1 = 0.1^\circ\), \(\phi_2 = 0.2^\circ\), \(\phi_3 = 0.3^\circ\). We observe that the outage behaviors of users are sensitive to the shadowing condition of satellite‑terrestrial channels. It is shown that the shadowing degrades network performance significantly. Frequent heavy shadowing results in a increasing outage performance, since the higher shadowing severities correspond to worse propagation conditions. As the value of channel shadowing parameter, i.e., \(b\), \(m\), and \(\Omega\) decreases, the outage performance of terrestrial users is becoming much worse seriously. This is due to the fact that both LoS component and multipath component become smaller for NOMA‑based satellite network.

![Figure 3: Outage probability versus the transmit SNR.](图片占位符_Fig3)

Fig. 3 plots the outage probability versus the transmit SNR with different angles between the beam center and users for experiencing FHS. One can observe from figure that with the angles increasing, the outage behaviors of terrestrial users are becoming much worse. This is due to the fact that with the increase of angles, the users are getting closer to the edge of the beam relative to satellite. As a result, to obtain better system performance, we should adjust the angle of satellite to target the terrestrial users from the perspective of service quality.

---



# Spatially Random Relay Selection for Cooperative NOMA Networks

In this section, our numerical results are provided for characterizing the outage performance of these two kinds of RS schemes. Monte Carlo simulation parameters used in this section are summarized in Table II [12, 42], in which BPCU is short for bit per channel use. The complexity‑vs‑accuracy tradeoff parameter is \(N = 15\). Except FD/HD‑based NOMA RRS schemes, the performance of OMA‑based RS scheme is also shown as a benchmark for comparison, where the total communication process is finished in four slots. In the first slot, the BS sends information \(x_1\) to relay \(R_i\) and send \(x_2\) to \(R_i\) in the second slot. In the third and fourth slot, \(R_i\) decodes and forwards the information \(x_1\) and \(x_2\) to \(D_1\) and \(D_2\), respectively. Adding the performance of AF‑based RS schemes for comparison will further enrich this paper, but this is beyond the scope of this paper. Note that NOMA users with low target data rate can be applied to the IoT scenarios, i.e., the low energy consumption, small packet service and so on.

**TABLE II**: Table of Parameters for numerical results.

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^6\) iterations |
| Power allocation coefficients of NOMA | \(a_1 = 0.2, a_2 = 0.8\) |
| Targeted data rates | \(R_{D_1} = 1, R_{D_2} = 0.1\) BPCU |
| Pass loss exponent | \(\alpha = 2\) |
| The radius of a disc region | \(R_D = 2\) m |
| The distance between the BS and \(D_1\) | 10 m |
| The distance between the BS and \(D_2\) | 12 m |

### A. Single‑stage Relay Selection Scheme

In this subsection, the FD/HD‑based NOMA RRS schemes and OMA‑based RS schemes are regarded as the baselines for comparison purposes.

![Figure 2: Outage probability versus the transmit SNR for SRS scheme with \(K = 2\); \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU and \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB.](图片占位符_Fig2)

Fig. 2 plots the outage probability of SRS scheme versus SNR for a simulation setting with \(K = 2\) and \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB. The black and blue solid curves are the SRS scheme for FD/HD NOMA, corresponding to the approximate results derived in (12) and (13), respectively. The dash dotted curves represent the approximate outage probabilities of RRS schemes for FD/HD NOMA derived in (30) and (31), respectively. Obviously, the outage probability curves match precisely with the Monte Carlo simulation results. It is observed that the performance of FD‑based NOMA SRS scheme is superior to HD‑based NOMA scheme on the condition of low SNR region. The reason is that loop interference is not the dominant impact factor for FD cooperative NOMA in the low SNR region. Moreover, the outage performance of the HD‑based NOMA SRS scheme outperforms the HD‑based RRS scheme. Another observation is that HD‑based NOMA SRS scheme is superior to OMA‑based RS scheme. This is due to the fact that HD‑based NOMA RS schemes is capable of enhancing the spectral efficiency compared to OMA. The asymptotic outage probability curves of the SRS schemes for FD/HD NOMA are plotted according to the analytical results in (33) and (34), respectively. One can observe that the asymptotic curves well approximate the analytical performance curves in the high SNR region. It is worth noting that an error floor exists in the FD‑based NOMA SRS scheme, which verifies the conclusion in Remark 1 and obtain zero diversity order. This is due to the fact that there is the loop interference in FD NOMA.

![Figure 3: Outage probability versus the transmit SNR for SRS scheme with the different target rates; \(K = 2\) and \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB.](图片占位符_Fig3)

Fig. 3 plots the outage probability of SRS scheme with different target rates. One can observe that adjusting the target rates of NOMA users will affect the outage behaviors of the FD/HD‑based SRS schemes. As the value of target rates increases, the superior of FD/HD‑based NOMA SRS schemes becomes not obvious. It is worth noting that based on the application requirements of different scenarios, the setting of reasonable target rates for NOMA users is prerequisite.

![Figure 4: Outage probability versus the transmit SNR for SRS scheme with \(K = 2,3,4\); \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU and \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB.](图片占位符_Fig4)

Fig. 4 plots the outage probability of SRS scheme versus SNR for a simulation setting with \(K = 2,3,4\) relays and \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB. As can be seen that the analytical curves perfectly match with the simulation results, while the approximations match the analytical performance curves in the high SNR region. It is shown that the number of relays in the networks considered strongly affect the performance of FD/HD‑based NOMA SRS schemes. With the number of relays increasing, the lower outage probability are achieved by this RS scheme. This is because more relays bring higher diversity gains, which improves the reliability of the cooperative networks. Another observation is that the HD‑based NOMA SRS scheme provides a diversity order that is equal to the number of the relays \((K)\), which verifies the conclusion in Remark 2.

![Figure 5: Outage probability versus the transmit SNR for SRS scheme with \(K = 3\); \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU.](图片占位符_Fig5)

As a further development, Fig. 5 plots the outage probability of SRS scheme versus different values of LI from \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB to \(\mathbb{E}\{|h_{LI}|^2\} = 5\) dB. As observed from the figure, we can see that the value of LI also strongly affect the performance of FD‑based SRS scheme for NOMA, while the HD‑based SRS scheme is not affected. This is due to the fact that LI is not existent for the HD‑based SRS scheme with \(\varpi = 0\). As the value of LI becomes larger, the outage performance of the FD‑based SRS scheme becomes more worse. In consequence, it is significant to consider the influence of LI in the practical FD NOMA networks.

![Figure 6: System throughput in delay‑limited transmission mode versus SNR for the SRS scheme.](图片占位符_Fig6)

Fig. 6 plots system throughput versus SNR in delay‑limited transmission mode for the different number of relays from \(K = 2\) to \(K = 4\) with \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB. The blue solid and red dashed curves represent throughput of SRS scheme for FD/HD NOMA networks which are obtained from (41) and (42), respectively. One can observe that the FD‑based SRS scheme achieves a higher throughput compared to the HD‑based SRS scheme for NOMA networks. This is because that the value of LI has a smaller influence for the outage behavior of FD NOMA in the low SNR region. Furthermore, the FD/HD‑based NOMA SRS schemes outperform OMA‑based RS scheme in terms of system throughput. This is due to the fact that NOMA‑based SRS scheme can provide more spectrum efficiency than OMA‑based SRS scheme. As the number of relays becomes larger, the FD/HD‑based SRS schemes can improve the system throughput. This phenomenon can be explained as that a lower outage probability can be obtained by the FD/HD‑based SRS schemes. In addition, Fig. 6 further give system throughput in delay‑limited transmission mode for the different values of LI with \(K = 3\). As can be observed that increasing the values of LI from \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB to \(\mathbb{E}\{|h_{LI}|^2\} = 5\) dB reduces the system throughput. This phenomenon indicates that it is of significance to consider the impact of LI for FD‑based SRS scheme when designing practical cooperative NOMA systems.

### B. Two‑stage Relay Selection Scheme

In this subsection, except FD/HD‑based NOMA RRS scheme, the outage performance of OMA‑based RS scheme is also shown as a benchmark for comparison.

![Figure 7: Outage probability versus the transmit SNR for TRS scheme with \(K = 3\); \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU and \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB.](图片占位符_Fig7)

Fig. 7 plots the outage probability of TRS scheme versus SNR with setting to be \(K = 3\) and \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB. The approximate analytical curves of the TRS schemes for FD/HD NOMA are plotted based on (28) and (29), respectively. As can be observed from the figure, the analytical curves match perfectly with Monte Carlo simulation results. We confirm that the higher outage performance can be obtained by FD‑based NOMA TRS scheme in the low SNR region. This is due to fact that there is a low loop interference for FD‑based TRS scheme and does not suffer from bandwidth‑loss influence. One can observe that the outage behaviors of FD/HD‑based NOMA TRS schemes outperform OMA‑based RS scheme. The asymptotic outage probability curves of FD/HD‑based NOMA TRS scheme are plotted according to (35) and (36), which are practically indistinguishable from the analytical results. It is also observed that the FD‑based TRS scheme for NOMA converges to an error floor and obtains the zero diversity, which is due to the fact that the loop interference exists at the relay. This phenomenon is confirmed by the insights in Remark 3. However, the HD‑based TRS scheme for NOMA overcomes the problem of zero diversity inherent to FD‑based scheme.

![Figure 8: Outage probability versus the transmit SNR for TRS scheme with different target rates; \(K = 3\) and \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB.](图片占位符_Fig8)

As shown in Fig. 3, Fig. 8 plots the outage probability of TRS scheme with different target rates. It is shown that when the target rates of NOMA users is reduced, the FD/HD‑based NOMA TRS schemes is capable of providing better outage performance. We confirm that the IoT scenarios (i.e., small packet service) considered can be supported by the NOMA‑based RS schemes.

![Figure 9: Outage probability versus the transmit SNR for TRS scheme with \(K = 2,3,4\); \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU and \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB.](图片占位符_Fig9)

Fig. 9 plots the outage probability of TRS scheme versus SNR for a simulation setting to be \(K = 2,3,4\) relays and \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB. We observed that the number of relays affect the performance of TRS scheme. With the number of relays increasing, the superiority of FD/HD‑based NOMA TRS schemes is apparent and the lower outage probabilities are obtained. We also see that the HD‑based RS scheme is capable of achieving a diversity order of \(K\), which confirms the insights in Remark 4. From a practical perspective, it is important to consider multiple relays in the networks when designing the NOMA RS systems.

![Figure 10: Outage probability versus the transmit SNR for TRS scheme with \(K = 3\); \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU.](图片占位符_Fig10)

Fig. 10 plots the outage probability of the TRS scheme versus different values of LI from \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB to \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB. We also can observe that with the value of LI increasing, the superior of outage performance for the FD‑based TRS scheme is not existent.

![Figure 11: System throughput in delay‑limited transmission mode versus SNR for the TRS scheme with \(R_{D_1} = 1\), \(R_{D_2} = 0.1\) BPCU.](图片占位符_Fig11)

Fig. 11 plots system throughput versus SNR in delay‑limited transmission mode for the different number of relays from \(K = 2\) to \(K = 4\) with \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB. The solid black and dashed magenta curves represent throughput of TRS for FD/HD NOMA networks which are obtained from (41) and (42), respectively. We can also observe that FD‑based NOMA TRS scheme has a higher throughput than HD‑based scheme in the low SNR region. The reason is that the FD‑based TRS scheme is capable of achieving a lower outage probability compared to HD‑based scheme. Moreover, the throughput of FD/HD‑NOMA TRS schemes precedes that of OMA‑based RS scheme. Additionally, it is worth pointing out that adjusting the size of target data rate (i.e., \(R_{D_1}\) and \(R_{D_2}\)) will affect the system throughput for delay‑limited transmission mode. The main performance of TRS scheme trends follow those in Fig. 6. Additionally, as can be seen from the figure that increasing the values of LI from \(\mathbb{E}\{|h_{LI}|^2\} = -20\) dB to \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB reduces the system throughput and the existence of the throughput ceilings in the high SNR region. This is due to the fact that the FD‑based TRS scheme converges to the error floor.

---



# Modeling and Analysis of Two-Way Relay Non-Orthogonal Multiple Access Systems

In this section, numerical results are provide to substantiate the system performance and investigate the impact levels of IS on outage probability and ergodic rate for TWR‑NOMA. Monte Carlo simulation parameters used are summarized in Table I, where BPCU is short for bit per channel use. Due to the reciprocity of channels between user groups (i.e., \(G_1\) or \(G_2\)) and \(R\), the outage behaviors and ergodic rates of \(x_1\) and \(x_2\) in \(G_1\) are presented to illustrate availability of TWR‑NOMA. Without loss of generality, the power allocation coefficients of \(x_1\) and \(x_2\) are set as \(a_1 = 0.8\) and \(a_2 = 0.2\) respectively. \(\Omega_1\) and \(\Omega_2\) are set to be \(\Omega_1 = d_1^{-\alpha}\) and \(\Omega_2 = d_2^{-\alpha}\), respectively. The performance of conventional TWR‑OMA is shown as a benchmark for comparison, in which the total communication process can be finished in five slots. In the first slot, the user nodes in \(G_1\), i.e., \(D_1\) and \(D_2\) sends signal \(x_1\) and \(x_2\) to \(R\). Meanwhile, the user nodes in \(G_2\), i.e., \(D_3\) and \(D_4\) sends signal \(x_3\) and \(x_4\) to \(R\). After completing the exchange of information, \(R\) sends signal \(x_3\) and \(x_4\) to \(D_1\) and \(D_2\) in the second and third slots, respectively. Then \(R\) sends signal \(x_1\) and \(x_2\) to \(D_3\) and \(D_4\) in the fourth and fifth slots, respectively. Except power allocation coefficients, other simulation parameters of TWR‑OMA is similar to that of TWR‑NOMA. It is worth pointing out that the signals are transmitted at full power for TWR‑OMA.

**TABLE I**  
TABLE OF PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^5\) iterations |
| Power allocation coefficients | \(a_1 = 0.8, a_2 = 0.2, a_3 = 0.8, a_4 = 0.2\) |
| Distances from users to \(R\) | \(d_1 = 10\) m, \(d_2 = 12\) m, \(d_3 = 10\) m, \(d_4 = 12\) m |
| Target rates | \(R_1 = 0.1, R_2 = 0.01, R_3 = 0.1, R_4 = 0.01\) BPCU |
| Path loss exponent | \(\alpha = 2\) |

### A. Outage Probability

![Figure 2: Outage probability versus the transmit SNR, with \(\sigma_1 = \sigma_2 = 0.01\), \(R_1 = 0.1\), \(R_2 = 0.01\) BPCU, and \(\Omega_I = -20\) dB.](图片占位符_Fig2)

Fig. 2 plots the outage probabilities of \(x_1\) and \(x_2\) with both ipSIC and pSIC versus SNR for simulation setting with \(\varpi_1 = \varpi_2 = 0.01\) and \(\Omega_I = -20\) dB. The solid and dashed curves represent the exact theoretical performance of \(x_1\) and \(x_2\) for both ipSIC and pSIC, corresponding to the results derived in (9), (10) and (12), (13), respectively. Apparently, the outage probability curves match perfectly with Monte Carlo simulation results. As can be observed from the figure, the outage behaviors of \(x_1\) and \(x_2\) for TWR‑NOMA are superior to TWR‑OMA in the low SNR regime. This is due to the fact that the influence of IS is not the dominant factor at low SNR. Hence in this scenario, NOMA systems should work as much as possible at low SNR regime, such as, the wide coverage in rural areas and cell edge scenarios. Another observation is that the pSIC is capable of enhancing the performance of NOMA compare to the ipSIC. In addition, the asymptotic curves of \(x_1\) and \(x_2\) with ipSIC/pSIC are plotted according to (15), (16) and (17), (18), respectively. It can be seen that the outage behaviors of \(x_1\) and \(x_2\) converge to the error floors in the high SNR regime. The reason can be explained that due to the impact of residual interference by the use of ipSIC, \(x_1\) and \(x_2\) result in zero diversity orders. Although the pSIC is carried out in TWR‑NOMA system, \(x_1\) and \(x_2\) also obtain zero diversity orders. This is due to the fact that when the relay first detect the strongest signal in the first slot, it will suffer interference from the weaker signal. This process is similar to the uplink NOMA [36]. Additionally, this observation verifies the conclusion Remark 1 in Section III.

![Figure 3: Outage probability versus the transmit SNR, with the different impact levels of IS from \(\varpi_1 = \varpi_2 = 0\) to \(\varpi_1 = \varpi_2 = 0.1\), \(R_1 = 0.1\), \(R_2 = 0.01\) BPCU, and \(\Omega_I = -20\) dB.](图片占位符_Fig3)

Fig. 3 plots the outage probabilities of \(x_1\) and \(x_2\) versus SNR with the different impact levels of IS from \(\varpi_1 = \varpi_2 = 0\) to \(\varpi_1 = \varpi_2 = 0.1\). The solid and dashed curves represent the outage behaviors of \(x_1\) and \(x_2\) with ipSIC/pSIC, respectively. As can be seen that when the impact level of IS is set to be \(\varpi_1 = \varpi_2 = 0\), there is no IS between \(A_1\) and \(A_2\) at the relay, which can be viewed as a benchmark. Additionally, one can observed that with the impact levels of IS increasing, the outage performance of TWR‑NOMA degrades significantly. As a consequence, it is crucial to hunt for efficient strategies for suppressing the effect of interference between antennas.

![Figure 4: Outage probability versus the transmit SNR, with different values of residual IS from \(-20\) dB to \(0\) dB, \(\varpi_1 = \varpi_2 = 0\), \(R_1 = 0.1\), \(R_2 = 0.01\) BPCU.](图片占位符_Fig4)

Fig. 4 plots the outage probabilities versus SNR with different values of residual IS from \(-20\) dB to \(0\) dB. It can be seen that the different values of residual IS affects the performance of ipSIC seriously. Similarly, as the values of residual IS increases, the preponderance of ipSIC is inexistent. When \(\Omega_I = 0\) dB, the outage probabilities of \(x_1\) and \(x_2\) will be in close proximity to one. Therefore, it is important to design effective SIC schemes for TWR‑NOMA.

![Figure 5: System throughput in delay‑limited transmission mode versus SNR with ipSIC/pSIC, \(R_1 = 0.1\), \(R_2 = 0.01\) BPCU, \(\varpi_1 = \varpi_2 = 0.01\).](图片占位符_Fig5)

Fig. 5 plots system throughput versus SNR in delay‑limited transmission mode for TWR‑NOMA with different values of residual IS from \(-20\) dB to \(-10\) dB. The blue solid curves represent throughput for TWR‑NOMA with both pSIC and ipSIC, which can be obtained from (19). One can observe that TWR‑NOMA is capable of achieving a higher throughput compared to TWR‑OMA in the low SNR regime, since it has a lower outage probability. Moreover, the figure confirms that TWR‑NOMA converges to the throughput ceiling in the high SNR regime. Additionally, it is worth noting that ipSIC considered for TWR‑NOMA will further degrade throughput with the values of residual IS becomes larger in high SNR regimes.

### B. Ergodic Rate

![Figure 6: Ergodic rate versus the transmit SNR with ipSIC/pSIC, \(\varpi_1 = \varpi_2 = 0.01\), and \(\Omega_I = -20\) dB.](图片占位符_Fig6)

Fig. 6 plots the ergodic rate of \(x_1\) and \(x_2\) for TWR‑NOMA versus SNR and the values of SI are assumed to be \(\varpi_1 = \varpi_2 = 0.01\), and \(\Omega_I = -20\) dB. The blue and red dash‑dotted curves represent the achievable rate of \(x_1\) and \(x_2\) with ipSIC/pSIC for TWR‑NOMA, respectively, which considers IS between \(A_1\) and \(A_2\) at the relay. The blue and red solid curves represent ergodic rates of \(x_1\) and \(x_2\) with ipSIC/pSIC according to (22), (23) and (25), (26), respectively. We can observe that the ergodic rates of \(x_1\) and \(x_2\) with pSIC are larger than that of \(x_1\) and \(x_2\) with ipSIC. This is due to the fact that pSIC can provide more performance gain than ipSIC. In addition, due to the influence of interference, \(x_1\) and \(x_2\) converge to the throughput ceilings in high SNR regimes, which verifies the conclusion Remark 3 in Section IV.

![Figure 7: System throughput in delay‑tolerant transmission mode versus SNR with ipSIC/pSIC, \(\varpi_1 = \varpi_2 = 0.01\) and \(\Omega_I = -20\) dB.](图片占位符_Fig7)

Fig. 7 plots the system throughput versus SNR in delay‑tolerant transmission mode for TWR‑NOMA. The blue solid curves represent system throughput for TWR‑NOMA with ipSIC/pSIC, which can be obtained from (19). The system throughput of IS‑based is selected to be the benchmark denoted by the red dash‑dotted curves. It is observed that TWR‑NOMA can achieve a higher throughput in the absence of IS at the relay. Hence, we need to find an effective way to restrain IS for both antennas at the relay.

### C. Energy Efficiency

![Figure 8: System throughput in delay‑limited/tolerant transmission mode versus SNR with ipSIC/pSIC, where \(P_u = P_r = 10\) W, and \(T = 1\).](图片占位符_Fig8)

Fig. 8 plots energy efficiency of TWR‑NOMA systems versus SNR with delay‑limited/tolerant transmission modes. The red solid curves represent system energy efficiency for the delay‑limited transmission mode with ipSIC/pSIC, respectively, which can be obtained from (19) and (34). The blue curves represent system energy efficiency for the delay‑tolerant transmission mode with ipSIC/pSIC, respectively, which can be obtained from (32) and (34). It is can be seen that TWR‑NOMA with ipSIC/pSIC in delay‑limited transmission mode have almost the same energy efficiency. Additionally, we can observe that the energy efficiency of TWR‑NOMA with pSIC is superior to ipSIC in high SNR regimes for the delay‑tolerant transmission.

---



# Exploiting Full/Half-Duplex User Relaying in NOMA Systems

In this section, simulation results are provided to validate our analytical expressions derived in the previous section, and further evaluate the performance of FD/HD user relaying in NOMA systems. Without loss of generality, we assume that the distance between BS and \(D_2\) is normalized to unity, i.e. \(\Omega_{SD_2} = 1\). \(\Omega_{SD_1} = d^{-\alpha}\) and \(\Omega_{D_1D_2} = (1 - d)^{-\alpha}\), where \(d\) is the normalised distance between BS and \(D_1\) setting to be \(d = 0.3\) and \(\alpha\) is the pathloss exponent setting to be \(\alpha = 2\). The power allocation coefficients of NOMA are \(a_1 = 0.2\) and \(a_2 = 0.8\) for \(D_1\) and \(D_2\), respectively.

### A. Without Direct Link

For user relaying without direct link, the target rate is set to be \(R_1 = 3\), \(R_2 = 0.5\) bit per channel use (BPCU) for \(D_1\) and \(D_2\), respectively. The performance of conventional OMA is shown as a benchmark for comparison, in which the total communication process is finished in three slots. In the first slot, the BS sends information \(x_1\) to \(D_1\) and sends \(x_2\) to \(D_1\) in the second slot. In the last slot, \(D_1\) decodes and forwards the information \(x_2\) to \(D_2\).

![Figure 2: Outage probability versus the transmit SNR without direct link.](图片占位符_Fig2)

1) Outage Probability: Fig. 2 plots the outage probability of two users versus SNR without direct link and the value of LI is assumed to be \(\mathbb{E}[|h_{LI}|^2] = -15\) dB. The exact theoretical curves for the outage probability of two users for FD/HD NOMA are plotted according to (10), (14) and (12), (17), respectively. Obviously, the exact outage probability curves match precisely with the Monte Carlo simulation results. It is observed that the outage performance of FD NOMA exceeds HD NOMA and OMA on the condition of low SNR region. This is because LI is not dominant impact factor in the low SNR region for FD NOMA and answers the first question we raised in the introduction part. Especially, one can also observed that the outage behavior of \(D_2\) for HD NOMA outperforms HD OMA [32, eq. (8)]. The asymptotic outage probability curves of two users for HD NOMA are plotted according to (20) and (22), respectively. The asymptotic curves well approximate the exact performance curves in the high SNR region. It is shown that error floors exist in FD NOMA, which verify the conclusion in Remark 3 and obtain zero diversity order. This is due to the fact that there is loop interference in FD NOMA. Another observation is that HD NOMA and OMA are superior to FD NOMA in the high SNR region. Therefore, we can select different operation mode for user relaying according to the different SNR levels in practical cooperative NOMA systems.

![Figure 3: System throughput in delay‑limited transmission mode versus SNR with different values of LI without direct link.](图片占位符_Fig3)

Fig. 3 plots the system throughput versus SNR in delay‑limited transmission mode without direct link. The solid curves represent throughput for FD/HD NOMA without direct link which are obtained from (23) and (24), respectively. We can observe that FD NOMA achieves a higher throughput than HD NOMA and OMA, since FD NOMA has the low values of LI. It is worth noting that increasing the values of LI from \(-20\) dB to \(-10\) dB reduce the system throughput in high SNR region. This is because FD NOMA converges to an error floor in high SNR region.

![Figure 4: Rates versus the transmit SNR without direct link.](图片占位符_Fig4)

2) Ergodic Rate: Fig. 4 plots the ergodic sum rate of FD/HD NOMA without direct link versus SNR and the value of LI is assumed to be \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB. The red and blue solid curves denote the achievable rates of \(D_1\) for FD/HD NOMA, respectively. The dashdotted curves denote the achievable rates of \(D_2\) for FD/HD NOMA, respectively. One can observe that the achievable rate of \(D_1\) for FD NOMA is superior to HD NOMA in the low SNR region. This phenomenon can be also explained is that LI has little effect on achievable rate of \(D_1\) in the low SNR region. On the contrary, due to the influence of LI, the ergodic rate of \(D_1\) converge to a throughput ceiling in the high SNR region. Another observation is that the achievable rate of \(D_2\) for FD NOMA exceeds the HD NOMA. This is due to the fact that the communication process is completed over one slot time for FD NOMA. It is also shown that throughput ceilings exist in FD/HD NOMA for \(D_2\), which verify the conclusion in Remark 5. The dashed curves denote the asymptotic ergodic sum rate for FD/HD NOMA, corresponding to the analytical results derived in (40) and (41), respectively. An important observation is that FD NOMA can achieve the maximal ergodic sum rate corresponding to HD NOMA and OMA in the low SNR region. The reason is that FD NOMA can improve system spectrum efficiency in the low SNR region. This phenomenon answers the third question we raised in the introduction part.

### B. With Direct Link

For user relaying with direct link, the target rate is set to be \(R_1 = 2\), \(R_2 = 1\) BPCU for \(D_1\) and \(D_2\) respectively. The performance of conventional HD NOMA is shown as a benchmark for comparison, which has been discussed in [25].

![Figure 5: Outage probability versus the transmit SNR with direct link.](图片占位符_Fig5)

1) Outage Probability: Fig. 5 plots the outage probability of two users versus SNR and the value of LI is assumed to be \(\mathbb{E}\{|h_{LI}|^2\} = -15\) dB. The exact outage probability curves of two users for FD NOMA are given by Monte Carlo simulations and perfectly match with the analytical results derived in (10) and (27). The approximated outage probability curve for \(D_2\) is plotted according to (28) is practically indistinguishable from the exact expression. We observe that \(D_2\) obtains one diversity order by using the direct link, which overcomes the problem of zero diversity order inherent to FD cooperative systems. This phenomenon answers the second question we raised in the introduction part. More importantly, one can observe that the performance of FD NOMA is superior to HD NOMA in the low SNR region, whilst the performance is inferior to HD NOMA in the high SNR region. Additionally, for \(D_2\), considering the impact of RI between relaying link and direct link, we plots the corresponding outage probability of \(D_2\) based on (25) denoted by blue dash‑dotted curves. As can be seen from Fig. 5, these simulation results almost match with analytical result derived in (27) by utilizing the upper bound SINR in low SNR region. However, with the increase of RI levels \(\kappa\), the RI‑based simulation results for \(D_2\) converge to a constant and provide an error floor in high SNR region. Hence, the effect of RI should be carefully addressed in practical FD NOMA systems. Another observation is that the outage behavior of \(D_2\) for FD/HD NOMA outperforms HD OMA [39, eq. (13)]. That is due to the fact that NOMA can provide more spectral efficiency compared to OMA.

![Figure 6: Outage probability versus the transmit SNR for different values of LI with direct link.](图片占位符_Fig6)

Fig. 6 plots the outage probability of the two users versus different values of LI from \(-20\) dB to \(-10\) dB. We see that LI strongly affect the performance of FD NOMA systems. With the values of LI increasing, the superiority of FD NOMA is no longer apparent. Therefore, it is important to consider the influence of LI when designing practical FD NOMA systems.

![Figure 7: System throughput in delay‑limited transmission mode versus SNR with different LI with direct link.](图片占位符_Fig7)

Fig. 7 plots system throughput versus SNR in delay‑limited transmission mode with direct link. The solid curves, representing FD NOMA, is obtained from (29). The dashed curve, representing HD NOMA, is obtained from (30). Observe that FD NOMA also outperform HD NOMA in the low SNR region. The reason is that in low SNR region, the outage probability is small and has no effect on the throughput, which only depends on the fixed transmission rates at the BS.

![Figure 8: Rates versus the transmit SNR with direct link.](图片占位符_Fig8)

2) Ergodic Rate: Fig. 8 plots the ergodic sum rate of HD/FD NOMA with direct link versus SNR and the value of LI is assumed to be \(\mathbb{E}\{|h_{LI}|^2\} = -10\) dB. The dashed curves denote the asymptomatic ergodic sum rate for FD/HD NOMA based on the analytical results derived in (48) and (49), respectively. It is observed that the asymptomatic ergodic sum rate is larger for FD/HD NOMA in the low SNR region. This can be explained as the direct link between BS and \(D_2\) exists and improves system reliability. One can observed from figure, as the RI value increases, the achievable rate of \(D_2\) becomes smaller, such as, setting \(\kappa\) from 0.5 to 1. In addition to consider the effect of LI, it is also important to design effective rake receiver at \(D_2\) for FD NOMA system.

### C. Energy Efficiency

![Figure 9: System energy efficiency in delay‑limited transmission mode.](图片占位符_Fig9)

Fig. 9 plots the system energy efficiency versus SNR in delay‑limited transmission mode for user relaying in NOMA systems. The dashed curves, representing user relaying without direct link for FD/HD NOMA are obtained from (53), (23) and (54), (24) with throughput in delay‑limited transmission mode, respectively. The solid curves, representing user relaying with direct link for FD/HD NOMA are obtained from (53), (29) and (54), (30) with throughput in transmission mode, respectively. It can be seen that the energy efficiency of user relaying for FD/HD NOMA in delay‑limited transmission mode is \(\mathrm{FD} > \mathrm{HD}\) in the low SNR region. The reason is that FD NOMA can achieve larger throughput than that of HD NOMA at this transmission mode. This phenomenon answers the fourth question we raised in the introduction part.

![Figure 10: System energy efficiency in delay‑tolerant transmission mode.](图片占位符_Fig10)

Fig. 10 plots the system energy efficiency versus SNR in delay‑tolerant transmission mode for user relaying in NOMA systems. The dashed curves, representing user relaying without direct link for FD/HD NOMA are obtained from (40), (53) and (41), (54) with throughput in delay‑tolerant mode, respectively. The solid curves, representing user relaying with direct link for FD/HD NOMA are obtained from (48), (53) and (48), (54) with throughput in delay‑tolerant mode, respectively. We observe that user relaying with direct link has a higher energy efficiency compared to without direct link for FD/HD NOMA in the low SNR region. This is because that the direct link improves system throughput at this transmission mode. Additionally, it is worth noting that HD NOMA achieves the higher system energy efficiency in the high SNR region. This is due to the fact that HD NOMA can provide a larger system throughput, while FD NOMA converges to the throughput ceiling in the high SNR region.

---



# A Unified Framework for Non-Orthogonal Multiple Access

In this section, we focus on investigating a typical pair of users with random pairing. Monte Carlo simulation parameters used in this section are summarized in TABLE II [42], [44], where BPCU is short for bit per channel use and the pass loss exponent \(\alpha = 2\) aims to simplify simulation analysis. The complexity‑vs‑accuracy tradeoff parameter is set to be \(U = 15\) and simulation results are denoted by \(\bullet\). Additionally, the conventional OMA is selected to be a benchmark for comparison purposes. The target rate \(R_o\) for OMA satisfies the relationship with \(R_o = R_n + R_m\). Note that the setting of smaller target data rate for NOMA users can be applied into the Internet of Things (IoT) scenarios, which require low energy consumption, small packet service and so on.

**TABLE II**  
TABLE OF PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^6\) iterations |
| Carrier frequency | 1 GHz |
| Power allocation coefficients of NOMA | \(a_m = 0.8, a_n = 0.2\) |
| Target data rates | \(R_n = R_m = 0.01\) BPCU |
| Pass loss exponent | \(\alpha = 2\) |
| The radius of the user zone | \(R_D = 2\) m |

![Figure 2: The COP versus the transmit SNR, with \(K = 2\), \(M = 3\), \(n = 2\), \(m = 1\), \(R_D = 2\) m, \(R_n = R_m = 0.01\) BPCU.](图片占位符_Fig2)

Fig. 2 plots the COP of a pair of NOMA users (the \(m\)-th and \(n\)-th user) versus the transmit SNR with ipSIC/pSIC, where \(K = 2\). In particular, the different values of RI are set to be from \(-30\) dB to \(-20\) dB. The exact analytical curve for the outage probability of the \(m\)-th user is plotted according to (11). Furthermore, the exact analytical curves for the outage probability of the \(n\)-th user with both ipSIC and pSIC for EXF and ALF are plotted based on (14), (19) and (15), (20), respectively. Obviously, the exact outage probability curves match perfectly with Monte Carlo simulations results. It is observed that the outage performance of OMA is inferior to the \(n\)-th user with pSIC and superior to the \(m\)-th user. This is due to the fact that NOMA is also capable of providing better fairness since multiple users are served simultaneously, which is the same as the conclusions in [10] and [45]. Additionally, as can be observed from figure, the dashed curves represent the asymptotic COP of the \(m\)-th user and \(n\)-th user with pSIC for EXF and ALF, which can be obtained by numerically evaluating (26), (29) and (33). One can observe that the asymptotic outage probabilities are approximated to the analytical results in the high SNR regime. The dotted curves represent the asymptotic outage probabilities of the \(n\)-th user with ipSIC for EXF and ALF, which are calculated from (28) and (32), respectively. It is shown that the outage performance of the \(n\)-th user with ipSIC converges to an error floor and obtain zero diversity order, which verifies the insights in Remark 2 and Remark 3. Due to the influence of RI, the outage behavior of the \(n\)-th user with ipSIC is inferior to OMA. The reason is that the RI signal from imperfect cancelation operation is the dominant impact factor. With the value of RI increasing from \(-30\) dB to \(-20\) dB, the outage behavior of the \(n\)-th user is becoming more worse and deteriorating. More specifically, when \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -10\) dB, the outage probability of the \(n\)-th user will be always one. Hence the design of effective multiuser receiver algorithm is significant to improve the performance of NOMA networks in practical scenario.

Another important observation can be seen from Fig. 2, when the target rates of the \(n\)-th user for EXF and ALF are set to be equal, there are the identical outage probabilities. This is because when the target rate of \(n\)-th user is greater than or equal to that of the \(m\)-th user, the \(n\)-th user with ALF forcibly decode the message of itself without carrying out SIC operations, which will be seriously constrained by interference from the \(m\)-th user. Another scenario is that when the target rate of the \(n\)-th user is less than that of the \(m\)-th user, which will be discussed in the following.

![Figure 3: The COP versus the transmit SNR, with \(M = 3\), \(n = 2\), \(m = 1\), \(K = 1\), \(R_n = 0.1\), \(R_m = 0.5\) BPCU, \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -30\) dB.](图片占位符_Fig3)

As a further advance, Fig. 3 plots the COP versus SNR with unequal target rates for user pairing. More particularly, the target rates of the \(n\)-th user and \(m\)-th user satisfy the relationship \(R_n < R_m\). It is observed that the outage behavior of the \(n\)-th user with ALP has an advantage over that of the \(n\)-th user with EXF. Under this assumption, the \(n\)-th user tries to detect its own information without carrying out the SIC operation and it will suffer from less interference. Another observation is that the outage behavior of the \(n\)-th user with ipSIC also precede OMA and converge to the same error floor in the high SNR region. This behavior is caused by the fact that the RI signal is not the dominant factor.

![Figure 4: The COP versus the transmit SNR, with \(M = 3\), \(n = 2\), \(m = 1\), \(R_n = R_m = 0.01\) BPCU, \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -30\) dB.](图片占位符_Fig4)

Fig. 4 plots the COP versus SNR with the different number of subcarriers (i.e., \(K = 3\) and \(K = 1\)). For the special case with \(K = 1\), the unified NOMA framework is reduced into PD‑NOMA. The exact outage probability curve of the \(m\)-th user for PD‑NOMA is plotted according to (12). The exact outage probability curves of the \(n\)-th user with ipSIC and pSIC for both EXF and ALF are given by Monte Carlo simulations and precisely match with the analytical expressions which have been derived in (16), (17), (21) and (22), respectively. As can be observed from figure, the asymptotic outage probabilities of this pair of users for PD‑NOMA are also approximated with the analytical results in the high SNR regime. As can be observed that with the subcarriers \(K\) increasing, CD‑NOMA has a more steep slope and provide better outage performance relative to PD‑NOMA. This is due to the fact that CD‑NOMA is capable of achieving the higher diversity orders, which verify the conclusion in Remark 4 and Remark 6. Hence we can confirm that the diversity gains of CD‑NOMA are directly combined with the number of subcarriers.

![Figure 5: The COP versus the transmit SNR, with \(K = 2\), \(M = 3\), \(n = 2\), \(m = 1\), \(R_n = R_m = 0.01\) BPCU, \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -30\) dB.](图片占位符_Fig5)

Fig. 5 plots the COP versus SNR for different network radius and pass‑loss factors. As can be observed that with the decreased network radius, the better outage behaviors of the selected user pairing can be obtained. This is due to the fact that a smaller network radius results in a lower path‑loss. Similarly, if the pass‑loss factor is adjusted from \(\alpha = 3\) to \(\alpha = 2\), the better outage performance can also be achieved. As a consequence, from a practical perspective, the design of NOMA systems should be in conjunction with cell radius and pass‑loss exponent. Additionally, the setting of target rates for the users is critical in NOMA networks.

![Figure 6: The COP versus the transmit SNR, with \(M = 3\), \(n = 2\), \(m = 1\), \(K = 2\), \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -30\) dB.](图片占位符_Fig6)

Fig. 6 plots the outage probabilities versus SNR for different user target rates. We observe that as the target rate decreases, the lower outage probabilities can be achieved. This is due to the fact that the achievable rates are directly related to the target SNRs. It is beneficial to detect the superposed signals for the selected user pairing with smaller target SNRs. It is worth pointing out that the impact of practical scenario parameter frequency dependent factor \(\eta\) has been taken into account in the unified NOMA framework. Furthermore, the incorrect choice of \(R_n\) and \(R_m\) will lead to the improper outage behavior for the unified framework, which verifies the conclusion in Remark 6.

![Figure 7: The COP versus the transmit SNR, with \(M = 3\), \(n = 2\), \(m = 1\), \(K = 1\), \(R_n = R_m = 1\) BPCU, \(\mathbb{E}\{\|\mathbf{h}_I\|_2^2\} = -30\) dB.](图片占位符_Fig7)

In order to obtain tractable analytical results, Fig. 7 plots the COP versus SNR with frequency dependent factor \(\eta = 1\) where the target rates \(R_n\) and \(R_m\) for the user pair are set to be \(R_n = R_m = 1\) BPCU. As can be observed that the outage behavior of the \(n\)-th user with pSIC is also superior to that of the \(m\)-th user. This is due to the fact that we have \(n > m\) and the \(n\)-th user achieves a higher diversity order. Another observation is that the outage behavior of the \(n\)-th user with ipSIC exceeds OMA on the condition of low SNR region. This is because RI is not the main influence factor in the low SNR region. This phenomenon indicates that it is significant to select favorable network parameter. Apparently, optimizing \(\eta\) can enhance the network outage performance.

![Figure 8: COP of the user pairing versus the transmit SNR and \(\theta\) with \(M = 3\), \(n = 2\), \(m = 1\), \(R_n = R_m = 0.01\) BPCU.](图片占位符_Fig8)

To illustrate the impact of dynamic power factor on NOMA performance, Fig. 8 plots the COP of the selected user pairing versus SNR and \(\theta\), where \(\theta \in [0,1]\) is the dynamic power allocation factor. Especially, when \(a_n\) is set to be \(a_n = \theta\), \(a_m = 1 - \theta\). The exact analytical results with pSIC are calculated from (23). One can observed that the COP decreases as SNR increases, which is the same as the traditional trend, where the COP always decreases as the transmit SNR increases. The reason is that the COP of the selected user pairing is determined by the \(m\)-th user. Another observation is that the dynamic power allocation factor affect the optimal COP with different values of SNR. This phenomenon indicates that it is significant to select beneficial system parameters. Furthermore, optimizing the power allocation factor is capable of further enhancing the COP.

![Figure 9: System throughput versus the transmit SNR, with \(M = 3\), \(n = 2\), \(m = 1\).](图片占位符_Fig9)

Fig. 9 plots the system throughput versus SNR in the delay‑limited transmission mode. The solid black curves represent throughput of CD‑NOMA and PD‑NOMA with pSIC, which can be obtained from (38) and (39), respectively. The red and blue dash curves represent throughput of CD‑NOMA and PD‑NOMA with ipSIC for the different values of RI, respectively. We observe that CD‑NOMA attains a higher throughput compared to PD‑NOMA, since CD‑NOMA has the smaller outage probabilities. This is due to that CD‑NOMA is capable of attaining the larger diversity order than that of PD‑NOMA. Another observation is that increasing the values of RI from \(-30\) dB to \(-20\) dB will reduce the system throughput in high SNR region. This is because that CD/PD‑NOMA converge to the error floors in the high SNR region. In addition, it is worth noting that adjusting the size of target data rate (i.e., \(R_m\) and \(R_n\)) will affect the system throughput in delay‑limited transmission mode.

---


