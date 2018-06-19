# HT_Hawk

关于QKF版本:
	QKF是能够解算出姿态的，在低速下式准确的，高速下QKF扰动较大
	且和恒拓的飞控有一些不兼容
	
	几个问题：
		1 烧写完成后，或启动时有，时数据会发散，在复位后基本能恢复正常
		2 测量噪声R，观测噪声Q有点小毛病，会使得飞控的噪声比较大
		3 由于代码是从Matlab得到的，参考：
				https://github.com/trigger1996/AHRS_QKF
				https://github.com/hkbl1988/AHRS_EKF
		4 原计划是使用px4带的那套EKF的，但是那套移植完问题比这个还大，姿态完全不对，如果有成功的欢迎交流
		5 STM32F1算不动这套代码，原本控制频率400Hz要降到100Hz，而且原生的代码对油门有过处理，所以控制响应很慢，非常慢，慢得吓人，建议用STM32F4系列计算
		
	现在计划改用6050自带的DMP
		