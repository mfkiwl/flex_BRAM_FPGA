# Flex BRAM for FPGA

可灵活例化任意深度、位宽的 ROM/RAM 的 Verilog 模块。自动通过深度划分、位宽划分、窄位宽合并技术尽可能减少 BRAM 资源的占用量。

(work-in-progress)



- [x] 双端口 ROM : ROM_flex.sv
  - [x] 参数化配置初始值
  - [x] 深度划分：例如对于深度=10000 ，划分为 9*1024+784 ， 避免综合器使用深度=16384而造成浪费。
  - [x] 位宽划分：例如对于位宽=37 ，划分为 36+1 ，位宽=36会综合成 Xilinx BRAM36 ，位宽=1可能会综合成 reg ，从而节省 BRAM。
  - [x] 位宽折叠：例如对于 2x4096 的 ROM，本来可能综合成 4 个 BRAM18 ，折叠为 8x1024 后，只需占用 1 个 BRAM18
- [ ] 双端口 RAM : RAM_flex.sv
  - [x] 参数化配置初始值
  - [x] 深度划分
  - [x] 位宽划分
  - [ ] 位宽折叠
- [ ] 完善文档





