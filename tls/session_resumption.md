
建立一个TLS会话是比较耗时的，会话复用通过保存会话和复用会话状态加快TLS会话建立过程。
这里讨论老的（Session ID会话复用）和新的（Session Ticket会话复用，当前推荐的）
两种会话复用机制。