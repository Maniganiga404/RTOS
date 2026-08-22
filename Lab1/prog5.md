int rec_sum(int i)
{
    if(i<=1)
      return i;
    else
      return i + rec_sum(i-1);
}

int main(void)
{
    int sum =0;
    sum=rec_sum(10);
    
  return 0;
}

int rec_sum(int i)

{

   0:	b580      	push	{r7, lr}

   2:	b082      	sub	sp, #8

   4:	af00      	add	r7, sp, #0

   6:	6078      	str	r0, [r7, #4]

    if(i<=1)

   8:	687b      	ldr	r3, [r7, #4]

   a:	2b01      	cmp	r3, #1

   c:	dc01      	bgt.n	12 <rec_sum+0x12>

      return i;

   e:	687b      	ldr	r3, [r7, #4]

  10:	e007      	b.n	22 <rec_sum+0x22>

    else

      return i + rec_sum(i-1);

  12:	687b      	ldr	r3, [r7, #4]

  14:	3b01      	subs	r3, #1

  16:	4618      	mov	r0, r3

  18:	f7ff fffe 	bl	0 <rec_sum>

  1c:	4602      	mov	r2, r0

  1e:	687b      	ldr	r3, [r7, #4]

  20:	4413      	add	r3, r2

}

  22:	4618      	mov	r0, r3

  24:	3708      	adds	r7, #8

  26:	46bd      	mov	sp, r7

  28:	bd80      	pop	{r7, pc}