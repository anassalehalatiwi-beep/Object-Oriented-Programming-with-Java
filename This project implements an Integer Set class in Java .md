public class Intgerset {
	public  boolean [] a =new boolean[101] ;
    public Intgerset() {
    	for(int i=0;i<a.length;i++)
    		a[i]= false;
    }//constrcuter
    public  String toString() {
    	String s ="{ ";
    	for(int i=0;i<a.length;i++)
    	if(a[i]==true)
    		s+=i+",";
    	s=s.substring(0,s.lastIndexOf(","));
    	s+="}";
    	s.trim();
    	return s;
    }//toSTring
    public void Insertfun(int...A){
    	for(int i=0;i<A.length;i++)
        if (A[i] >= 0 && A[i] < a.length) {
        	a[A[i]]=true;}
    	}//insert fun
    
    	public void Deletefun(int...A){
        	for(int i=0;i<A.length;i++) 
            if (A[i] >= 0 && A[i] < a.length) 
            	a[A[i]]=false;
    	}//delete fun

    	public Intgerset Unouset(Intgerset s) {
    		Intgerset result = new Intgerset();
        	for(int i=0;i<a.length;i++)
        		if(a[i]==true || s.a[i]==true)
        			result.Insertfun(i);
        	return result;

    	}
    	//unou
    	public Intgerset Interection(Intgerset s) {
    		Intgerset result = new Intgerset();
        	for(int i=0;i<a.length;i++)
        		if(a[i]==true && s.a[i]==true)
        			result.Insertfun(i);
        	return result;
    	}//interection
    		
    	public Intgerset Complement() {
    		Intgerset result = new Intgerset();
        	for(int i=0;i<a.length;i++)
        		if(a[i]==false)
        			result.Insertfun(i);
        	return result ;
    	}//complement
    	
    	public int CountElemnt() {
    		int  count=0;
    		for(int i=0;i<a.length;i++)
    			if(a[i]==true)
    				count++;
    		return count ;
    	}//countelemnt
    	
    	
    	public  boolean Sarch (int x) {
    		for(int i=0;i<a.length;i++)
    			return a[x];
			return false;
    	}//Sarch
    	
    	public  boolean Emtey () {
    		if(CountElemnt()==0)
    			return true;
			return false;
    	}//Emtey
    	
    	public  int Max () {
    		int ma=-1;
    		for(int i=a.length-1;i>0;i--)
    			if(a[i]==true) 
    				return i;
    		return ma;
    				

    	}//max
    	public  int Min () {
    		int mi=-1;
    		for(int i=0;i<a.length;i++)
    			if(a[i]==true) 
    				return i;
    		return mi;
    				

    	}//min
    	
    	
    	
	public static void main(String[] args) {
		Intgerset op1 =new Intgerset()  ;
		Intgerset op2 =new Intgerset()  ;
		int array[] = {1,2, 17, 19, 99,30};
	    op1.Insertfun(array);
	    op2.Insertfun(2,3,34,54,5);
	    op1.Deletefun(1);
		System.out.println("op1"+op1.toString());
		System.out.println("op2"+op2.toString());
		System.out.println("Unou op1 && op2"+op1.Unouset(op2));
		System.out.println("Interection op1 && op2"+op1.Interection(op2));
		//System.out.println(Complement:-op1"+op1.complement());
		System.out.println("Count:-op1 ="+op1.CountElemnt());
		System.out.println("Emtey op1 ?"+op1.Emtey());
		System.out.println("Max op1 "+op1.Max());
		System.out.println("Min op1 "+op1.Min());
		
		


	}

}
