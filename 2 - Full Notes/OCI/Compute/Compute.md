**Date**: 2025-09-26 15:56

**Topics**: [[oci]] [[compute]]

**Category**: #oci #compute

## Notes :

### Compute 

- Virtual Machine 
- Bare Metal
- Dedicated Host (Own VM's , not shared)

	- AMD , INTEL , ARM processors are supported.

- preemptive VM's.

### Instance

![[Pasted image 20250926160405.png]]

- Live Migrate (No restart required) (In case of failure or maintenance)

### Scaling

1. Vertical Scaling
	- CPU , RAM etc
2. Horizontal/Auto Scaling
	- Add VM's of same shape if required , else scale down.
	- Easily match the traffic demand.


#### Horizontal Scaling

1. Create stamp :
![[Pasted image 20250926162559.png]]

2. Use the stamp to make the instance pool

![[Pasted image 20250926162536.png]]

3. Write auto scaling rules
![[Pasted image 20250926162504.png]]

## References :
