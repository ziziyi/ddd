# Hive定义UDF,对原表的数据进行清洗，去除引号 java
public class RemoveQuotesUDF extends UDF {	
	public Text evaluate(Text str){
		// validate 
		if(null == str.toString()){
			return new text() ; }
		// remove
		return new Text (str.toString().replaceAll("\"", ""))  ;
             }或者
               if(null == str){
			return null ;
		}if(null == str.toString()){
			return null ;}
             // remove
		return new Text (str.toString().replaceAll("\"", ""))  ;


	public static void main(String[] args) {
		System.out.println(new RemoveQuotesUDF().evaluate(new Text("\"31/Aug/2015:00:04:37 +0800\"")));}
                }
