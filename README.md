homework after java class
=======================  
1. First import maven project and commit the github
2. exercise classroom practice 
### random exercise  

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
### give you a age，then determine the age  

		Scanner sc = new Scanner(System.in);
		//age
		int age = sc.nextInt();
		
		if(age > 60)System.out.println("老人");
		
		if(age > 40) System.out.println("中年人");
		
		if(age > 17)System.out.println("青年人");
		
		if(age > 6)System.out.println("少年人");
		
		if(age > 0)System.out.println("儿童");
### print singular number from 0 to 100 and count  


		//计数
		int count = 0;
		for(int i = 0 ; i <= 100 ; i++) {
			if(i % 2 != 0) {
				System.out.println("singular " + i);
				count++;
			}
		}
		System.out.println(count);
algorithm of 吸血鬼
==========================   
## 要点分析  
1. 四位数是从 1000 - 9999（也就是 32的平方到99的平方） 
2.  
  > 设这个四位数为value，那么value = 1000a + 100b + 10c + d<br/>
  > 那么a,b,c,d四个数进行全排列有24种情况<br/>
  > 然后两个一组分为两组，去掉重复可以得到12种情况<br> 
  > 设第一个数为x，第二个数为y，由题可以得到关系value = x * y<br/>  
   

******************************  
<table>
  <tr>
    <th width=30px>x</th>
    <th width=30px>y</th>
  </tr>
  <tr>   
    <td align="center"> a&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp b</td>
    <td align="center"> c&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp d</td>
  </tr>
  <tr>
    <td align="center"> a&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp b</td>
    <td align="center"> d&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp c</td>
  </tr>
  <tr>
    <td align="center"> b&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp a</td>
    <td align="center"> c&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp d</td>
  </tr>
  <tr>
    <td align="center"> b&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp a</td>
    <td align="center"> d&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp c</td>
  </tr>
 <tr>
    <td align="center"> a&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp c</td>
    <td align="center"> b&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp d</td>
  </tr>
 <tr>
    <td align="center"> a&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp c</td>
    <td align="center"> d&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp b</td>
  </tr>
 <tr>
    <td align="center"> c&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp a</td>
    <td align="center"> b&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp d</td>
  </tr>
  <tr>
    <td align="center"> c&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp a</td>
    <td align="center"> d&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp b</td>
  </tr>
  <tr>
    <td align="center"> a&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp d</td>
    <td align="center"> b&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp c</td>
  </tr>
 <tr>
    <td align="center"> a&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp d</td>
    <td align="center"> c&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp b</td>
  </tr>
 <tr>
    <td align="center"> d&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp a</td>
    <td align="center"> b&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp c</td>
  </tr>
 <tr>
    <td align="center"> d&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp a</td>
    <td align="center"> c&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp b</td>
  </tr>
</table>    


  ### 按照十二种情况进行判断  

		public static void main(String[] args) {
		
		int[] iarray = new int[4];
		int time = (int) System.currentTimeMillis();
		for(int i = 1000 ; i < 9999 ; i++) { 
			iarray = f1(i);
			 if((iarray[3]*10+iarray[2])*(iarray[1]*10+iarray[0])==i){
                 System.out.println("吸血鬼数字为："+i+"="+(iarray[3]*10+iarray[2])+"*"+(iarray[1]*10+iarray[0]));
             }                        
             else if((iarray[3]*10+iarray[2])*(iarray[1]+iarray[0]*10)==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]*10+iarray[2])+"*"+(iarray[1]+iarray[0]*10));
             }
             else if((iarray[3]+iarray[2]*10)*(iarray[1]*10+iarray[0])==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]+iarray[2]*10)+"*"+(iarray[1]*10+iarray[0]));
             }
             else if((iarray[3]+iarray[2]*10)*(iarray[1]+iarray[0]*10)==i){
                 System.out.println("吸血鬼数字为："+i+"="+(iarray[3]+iarray[2]*10)+"*"+(iarray[1]+iarray[0]*10));
             }
             else if((iarray[3]*10+iarray[1])*(iarray[2]*10+iarray[0])==i){
                 System.out.println("吸血鬼数字为："+i+"="+(iarray[3]*10+iarray[1])+"*"+(iarray[2]*10+iarray[0]));
             }
             else if((iarray[3]*10+iarray[1])*(iarray[2]+iarray[0]*10)==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]*10+iarray[1])+"*"+(iarray[2]+iarray[0]*10));
             }
             else if((iarray[3]+iarray[1]*10)*(iarray[2]*10+iarray[0])==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]+iarray[1]*10)+"*"+(iarray[2]*10+iarray[0]));
             }
             else if((iarray[3]+iarray[1]*10)*(iarray[2]+iarray[0]*10)==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]+iarray[1]*10)+"*"+(iarray[2]+iarray[0]*10));
             }
             else if((iarray[3]*10+iarray[0])*(iarray[1]*10+iarray[2])==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]*10+iarray[0])+"*"+(iarray[1]*10+iarray[2]));
             }
             else if((iarray[3]*10+iarray[0])*(iarray[1]+iarray[2]*10)==i){
                 System.out.println("吸血鬼数字为："+i+"="+(iarray[3]*10+iarray[0])+"*"+(iarray[1]+iarray[2]*10));
             }
             else if((iarray[3]+iarray[0]*10)*(iarray[1]*10+iarray[2])==i){
                 System.out.println("吸血鬼数字为："+i+"="+(iarray[3]+iarray[0]*10)+"*"+(iarray[1]*10+iarray[2]));
             }
             else if((iarray[3]+iarray[0]*10)*(iarray[1]+iarray[2]*10)==i){
                 System.out.println("吸血鬼数字为： "+i+"="+(iarray[3]+iarray[0]*10)+"*"+(iarray[1]+iarray[2]*10));
             }
		}
		int time2 = (int) System.currentTimeMillis();
		System.out.println((time2 -time) + "ms");//花费了3ms
			
	}

	/**
	 * 进行拆分
	 */
	private static int[] f1(int i) {
		//四位数对每一位进行拆分存放数组
		
		int[] array = new int[4];
		for(int j = 3 ; j >= 0 ; j--)
		{
			array[j] = i % 10;
			i = i / 10;
		}
		return array;
		
	}
	} 
 **************************  
#### 时间复杂度和空间复杂度分析  
  + 时间复杂度：o（n2）
  + 空间复杂度：常量
  + 频度分析考虑最坏情况次数: 2\*4\*12\*9000 = 864000 
  + T（n）=2n * n + 2 
  
  回文数
==========================
## 要点分析  
  1. 负数 -121回文 121-
  2. 结尾为0的数520回文025
  3. 不能采用字符串反转比较025这种情况无法处理，所以只能进行数值操作按位取余运算   
	
**************************  
##   方法一
		传统方法取出每一位然后反转计算值，再进行比较这样可能会出现溢出的情况且运算次数较多


## 方法二对称进行比较   
		public boolean isPalindrome(int x) {
         if(x < 0 || x !=0 && x%10 == 0)return false;
         
         int temp = 0;
         while(x > temp) {
             temp = temp*10 + x%10;
             x = x/10;
         }
        return x == temp || x == temp/10;
    }
	时间复杂度：T（n） = 2\*2\n+2
	o(n) = log2n
	相较于第一种n就比较好