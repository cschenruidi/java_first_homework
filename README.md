homework after java class
=======================  
1. First import maven project and commit the github
2. exercise classroom practice 
##random exercise  
		
		boolean flag = true;
		while(flag) {
			int number = (int)(Math.random()*1000)+1;
			if(number %30 == 0) {
				System.out.println("可以被整除的数" + number);
				flag = false;
			}else {
				System.out.println("随机数" + number);
			}
		}
##give you a age，then determine the age
		Scanner sc = new Scanner(System.in);
		//age
		int age = sc.nextInt();
		
		if(age > 60)System.out.println("老人");
		
		if(age > 40) System.out.println("中年人");
		
		if(age > 17)System.out.println("青年人");
		
		if(age > 6)System.out.println("少年人");
		
		if(age > 0)System.out.println("儿童");
##print singular number from 0 to 100 and count
		//计数
		int count = 0;
		for(int i = 0 ; i <= 100 ; i++) {
			if(i % 2 != 0) {
				System.out.println("singular " + i);
				count++;
			}
		}
		System.out.println(count);
