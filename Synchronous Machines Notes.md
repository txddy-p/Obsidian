For 3$\phi$ systems ratings are always given as line to line.

## SM Rotor
- Cylindrical Rotor has 1 distributed winding  (high speed needs fewer # of poles)
	- stepped mmf waveform produced by single distributed winding in rotor

- Salient Pole Rotor has 1 concentrated winding 
	- Low speed applications because requires large # of poles and the large diameter can accommodate this
	- Salient => “Projecting or pointing outward”  
	-  Single concentrated winding produces square-wave mmf
- Rotor winding carries DC current


## Features: Torque Production
- Produced by tendency of rotor field to align with rotating stator field

## Operation of SM:
- Motor or Gen mode of operation:  
	- supply MW to or draw MW from Grid  
- Constant speed operation at: n s  
	- ns determined by grid frequency in Motor mode  
	- Shaft speed determines frequency in Gen mode  
- Import or export of mega-VARs  
	- Operation at leading or lagging power factor  
	- Achieved by controlling excitation current


## Operation of SM:  Genarator
- Elementary 2-pole synchronous generator has 3 distributed windings displaced by 120° from each other  
- When rotor excited with DC and rotated, field rotates and induces sinusoidal voltages in stator windings, phase-displaced by 120° in time with frequency ∝ to rotor speed.

## Operation of SM: Motor
- Constant speed operation  
- Speed determined by supply frequency and number of poles  
- Not self starting...
- Rotor vibrates when started direct on-line  
- Start as induction motor  
- Run up to $n_s$ with variable speed drive


### Equivalent CCT
![[Pasted image 20230606210108.png]]

![[Pasted image 20230606210203.png]]

![[Pasted image 20230606210337.png]]

![[Pasted image 20230606210408.png]]


## Open-circuit test:  
- Stator windings open circuit, rotor driven at rated speed, $I_f$ varied, $E_f$ measured  
- Open Circuit Characteristic of SM measured during open circuit test
![[Pasted image 20230606210721.png]]

## Short-circuit test:  
- Stator windings short circuited, rotor driven at rated speed, $I_f$ varied, $I_a$ measured  
• Short Circuit Characteristic of SM measured during open circuit test:  
$I_a$ vs $I_f$
![[Pasted image 20230606210927.png]]

![[Pasted image 20230606211839.png]]


![[Pasted image 20230606211934.png]]

# Phasor Diagram
![[Pasted image 20230606212119.png]]


## Phasor diagram: Gen Mode
![[Pasted image 20230606212301.png]]

![[Pasted image 20230606212423.png]]

## Phasor diagram: Motor Mode
![[Pasted image 20230606212805.png]]


## Power & Torque characteristics
Per phase power:
$$
\begin{align*}
S &= V_tI^{*}_{a}\\
P &= Re(S)\\
Q &= Im(S)
\end{align*}
$$

![[Pasted image 20230606213545.png]]


![[Pasted image 20230606214135.png]]

![[Pasted image 20230606214344.png]]
$P_{max}$ and $T_{max}$ can be increased by increasing $I_f$ which in turn increases $E_f$. The machine shouldn't be operated here forever this is just a stop-gap


- Developed torque is independent of speed!!!  
- Thus, SM runs at constant speed throughout load range


# PF variation
Assume Gen mode operation, at constant power and 𝑹𝒂 ≈ 𝟎
![[Pasted image 20230606215605.png]]

![[Pasted image 20230606220600.png]]

- Similarities
	- Stator configuration:  
		- (a) 3-phase distribution winding.  
		- (b) Stator windings is connected to the AC supply.

- Differences
- Rotor configuration
- IM
	- a) Field winding.
	- (b) Field winding excited by the distributed magnetic field rotates in the air-gap.
- SM
	- (a) Field winding/permanent magnet.
	- (b) Field winding is excited by a direct current (DC) from an external supply.


Synchronous machine are doubly excited machines because two electrical inputs are supplied from both the stator and rotor. The rotor carrying DC supply produces a constant flux. The rotor is initially fed some mechanical input which rotates in the direction of the magnetic field to a speed very close to the synchronous speed. After some magnetic field interaction, the synchronous motor rotates in synchronism with the frequency.

