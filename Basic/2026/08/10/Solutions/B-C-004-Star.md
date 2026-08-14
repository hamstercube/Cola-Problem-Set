#include <stdio.h>
 int main()
 {
     int t;
     scanf("%d", &t);   //测试用例数量
     while(t--)
     {
         int n;
         scanf("%d", &n);
         int a[55];
         int sum = 0;
         // freq[i]：记录数值i出现多少次，a_i<=1000
         int freq[1005] = {0};
         
         for(int i = 0; i < n; i++)
         {
             scanf("%d", &a[i]);
             sum += a[i];
             freq[a[i]]++;
         }
         
         int maxcnt = 0;
         int val = 0;
         //找出出现次数最多的数字以及它的次数
         for(int i = 1; i <= 1000; i++)
         {
             if(freq[i] > maxcnt)
             {
                 maxcnt = freq[i];
                 val = i;
             }
         }
         
         int ans;
         if(maxcnt <= (n + 1)/2)
         {
             ans = sum;
         }
         else
         {
             int take = 2*(n - maxcnt)+1;
             ans = take * val;
         }
         printf("%d\n", ans);
     }
     return 0;
 }