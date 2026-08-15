#include <stdio.h>
 int main()
 {
     int N;
     scanf("%d", &N);
     int vis[1001] = {0}; // vis[x]=1 代表数字x存在
     for(int i = 1; i <= N; i++)
     {
         int x;
         scanf("%d", &x);
         vis[x] = 1; // 标记这个数字出现过
     }
     // 先统计有多少个不同的数 M
     int M = 0;
     for(int i = 1; i <= 1000; i++)
     {
         if(vis[i] == 1) M++;
     }
     printf("%d\n", M);
     // 从小到大输出所有出现过的数字
     int first = 1;
     for(int i = 1; i <= 1000; i++)
     {
         if(vis[i] == 1)
         {
             if(first == 1)
             {
                 printf("%d", i);
                 first = 0;
             }
             else
             {
                 printf(" %d", i);
             }
         }
     }
     printf("\n");
     return 0;
 }
