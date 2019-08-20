## 代码分析

### AXI4

#### AXI ar
``` verilog
    else if (axi_arvalid_i && axi_arready_o)
    begin
        req_rd_q      <= (axi_arlen_i != 0);  
        req_len_q     <= axi_arlen_i - 8'd1;
        req_addr_q    <= axi_araddr_i + 32'd4;
        req_id_q      <= axi_arid_i;
        req_axburst_q <= axi_arburst_i;
        req_axlen_q   <= axi_arlen_i;
        req_prio_q    <= !req_prio_q;
    end
```

``` verilog
     input           axi_arvalid_i   //use
    ,input  [ 31:0]  axi_araddr_i    //use
    ,input  [  3:0]  axi_arid_i      //  use
    ,input  [  7:0]  axi_arlen_i     //  use 
    ,input  [  1:0]  axi_arburst_i   // not use
    ,output          axi_arready_o
```
#### 对AXI4 部分进行仿真 查看RAM的信号
1. 发送clk, rst 
2. ar部分发送读一个地址的命令
3. 主要查看ram部分的反应
4. 使用len为4查看一下反应

#### 
