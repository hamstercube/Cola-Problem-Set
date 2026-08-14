#include <stdio.h>
 int main()
 {
     int t;
     scanf("%d", &t);
     while(t--)
     {
         int n;
         scanf("%d", &n);
         long long w[105];
         for(int i = 1; i <= n; i++)
         {
             scanf("%lld", &w[i]);
         }
         // n 为奇数：不可能
         if(n % 2 == 1)
         {
             printf("NO\n");
             continue;
         }
         long long low = -1e18;   // k必须大于 low
         long long high = 1e18;   // k必须小于 high
         for(int i = 1; i <= n; i++)
         {
             if(i % 2 == 1)
             {
                 // 奇数下标：k < w[i]
                 if(w[i] < high) high = w[i];
             }
             else
             {
                 // 偶数下标：k > w[i]
                 if(w[i] > low) low = w[i];
             }
         }
         // 是否存在整数 k，满足 low < k < high
         if(low + 1 <= high - 1)
         {
             printf("YES\n");
         }
         else
         {
             printf("NO\n");
         }
     }
     return 0;
 }