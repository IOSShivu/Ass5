unc swapp(a:inout Int,b:inout Int) throws
{
  guard a>0 else{
    throw numError.negative
    return
  }
    let temp = a
    a = b
    b = temp
    print("a= \(a) b= \(b)")
}

enum numError:Error
{
  case negative
  var msg:String
  {
    switch self
    {
     
      case .negative:return"Error:Negatieve no is not allowed...";
    }
  }
}

do
{
 var a=6;
 var b=2;
  try swapp(a:&a, b:&b);  
}
catch
{
  if let error=error as?numError
  {
    print(error.msg);
  }
}

func FindMean(_ num : Double...)->Double
{
    var tot : Double = 0.0
    for n in num
    {
        tot+=n
    }
 return tot / Double(num.count)
}
var res=0.0
res=FindMean(1.7,2.4,3.0,4.9,5.5)
print("Mean: \(res) ")

 
 
