## *Recursion:*

f(ind) {

  if(ind == 0 || ind == 1)  return 1;

  return f(ind-1) + f(ind+1);

}
