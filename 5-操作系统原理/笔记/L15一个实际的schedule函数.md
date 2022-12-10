# L15一个实际的schedule函数
```C
//在kernel/sched.c中
//counter同时作为时间片和优先级
void Schedule(void) {
    while(1) { 
        c=-1; next=0; i=NR_TASKS;
        p =& task[NR_TASKS];
        while(--i){
            //求最大的counter
            if(*p->state == TASK_RUNNING&&(*p)->counter>c)
                c=(*p)->counter, next=i;
        }
        if(c) 
            break; //找到了最大的counter
        
        for(p=&LAST_TASK;p>&FIRST_TASK;--p)
            (*p)->counter=((*p)->counter>>1)+(*p)->priority; 
    }
    switch_to(next);
}

```