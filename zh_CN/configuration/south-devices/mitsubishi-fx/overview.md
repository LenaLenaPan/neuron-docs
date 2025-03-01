# 概览

Mitsubishi FX 插件用于通过 FX 编程口访问三菱的 FX0、FX2、FX3 等系列 PLC。

## 设备配置

| 字段     | 说明                           |
| -------- | ------------------------------ |
| **timeout**  | 连接超时时间，默认为3000毫秒 |
| **interval** | 指令发送间隔，默认为20毫秒   |
| **device**   | 串口设备路径                |
| **stop**     | 停止位，默认为1             |
| **parity**   | 校验位，默认为 even         |
| **baud**     | 波特率，默认9600            |
| **data**     | 数据位，默认为7             |

## 支持的数据类型

* INT16
* UINT16
* INT32
* UINT32
* FLOAT
* DOUBLE
* BIT
* STRING

### 地址格式用法

### 地址格式

> AREA ADDRESS\[.BIT]\[.LEN\[H]\[L]]</span>

#### AREA ADDRESS

| 区域 | 数据类型 | 属性  | 备注                                   |
| ---- | -------- | ----- | -------------------------------------- |
| X    | bit      | 读/写 | 输入继电器  (FX3U)                 |
| Y    | bit      | 读/写 | 输出继电器 (FX3U)                  |
| M    | bit      | 读/写 | 内部继电器 (FX3U)                  |
| SM   | bit      | 读/写 | 特殊寄存器 (FX3U)                  |
| S    | bit      | 读/写 | 状态继电器(FX3U)                   |
| TS   | bit      | 读/写 | 定时器触点 (FX3U)                  |
| CS   | bit      | 读/写 | 计数器触点 (FX3U)                  |
| TN   | 所有类型 | 读/写 | 定时器当前值 (FX3U)                 |
| CN   | 所有类型 | 读/写 | 计数器当前值 (FX3U)                 |
| D    | 所有类型 | 读/写 | 数据寄存器 (FX3)                   |

#### .BIT

只可用于**非 bit 类型区域**，表示读取指定地址的指定二进制位，二进制位索引区间为[0, 15]。

| 地址  | 数据类型 | 说明                       |
| ----- | -------- | -------------------------- |
| D20.0 | bit      | D 区域，地址为 20，第 0 位 |
| D20.2 | bit      | D 区域，地址为 20，第 2 位 |

#### .LEN\[H]\[L]

当数据类型是 string 类型时，**.LEN** 表示的是字符串长度；可以选填 **H**和 **L** 表示两种字节顺序，默认的是 **H** 的字节顺序。

### 地址示例

| 地址      | 数据类型 | 说明                                           |
| --------- | -------- | -------------------------------------------- |
| X0    | bit      | X 区域，地址为 0    |
| X1    | bit      | X 区域，地址为 1    |
| Y0    | bit      | Y 区域，地址为 0    |
| Y1    | bit      | Y 区域，地址为 1    |
| D100  | int16    | D 区域，地址为 100  |
| D120  | uint16   | D 区域，地址为 120  |
| D200  | uint32   | D 区域，地址为 200  |
| D10   | float    | D 区域，地址为 10   |
| D20   | double   | D 区域，地址为 20   |
| D152.16L | string   | D 区域，地址为 1002，字符串长度为 16，字节顺序为 L |
| D183.16  | string   | D 区域，地址为 1003，字符串长度为 16，字节顺序为 H |
