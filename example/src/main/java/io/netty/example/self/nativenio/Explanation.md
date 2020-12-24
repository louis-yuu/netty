

1. Buffer.flip()的理解:
    在对一个Buffer写完之后，如果想要读取这个Buffer，必须要调用flip翻转一下，
    实际在做的东西就是将limit的值设置为position(当前Buffer写到哪了)，position
    的值设置为0，mark的值设置为-1。这样就可以从下标0开始读取Buffer了。

    源码注释:
          *   *{@link #flip} makes a buffer ready for a new sequence of
          *   channel-write or relative <i>get</i> operations: It sets the limit to the
          *   current position and then sets the position to zero.
          其中意思是指让buffer可以让channel去写(写到channel不也是要一一从这个buffer去读出来然后再写进去吗，
          不flip什么都读不到，又怎么写呢，这么去理解更好理解)