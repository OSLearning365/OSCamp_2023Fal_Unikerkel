## 第二周



本实验指导是为 2023 秋季 OS 训练营第三阶段 - 项目1：Unikernel 方向，而做的前期准备。这是第二周的练习内容，目标是在 ArceOS Unikernel OS 模式下，完成几个基本实验与附加练习，为支持多应用的实习任务做准备。

1. 基本实验：本指导书以增量的方式基本给出了 1 到 5 共 5 个实验的源码及过程，大家照着做一遍，以熟悉基本原理机制。
2. 附加练习：基于基本实验，根据自己的理解，增加一些实现，以达到练习要求目标。总共 6 个练习。

对完成实验和练习的过程要求：

1. 按照下节 ***环境准备*** 第 2 点要求分别建立分支，并 commit。
2. 成功的截图发到群里。
4. 仓库链接发邮件到 sun_ye@massclouds.com。**注意**：第一周发过邮件的同学，只要你的仓库未改，**不用**发邮件。我们保留了你们的仓库，可以直接去对应分支上查看各位的代码。所以请务必按照后面的要求建立分支和标记 commit 消息。



### 环境准备

1. Fork ArceOS 的工程，clone 到本地。工程链接如下：

   ```bash
   git@github.com:arceos-org/arceos.git
   ```

   通过 `git log` 查看 commit id 是否为 *51a42ea4d65a53bf6b43fc35a27a3ff1e9e284c7*。如果不是，回退到这个 commit，确保工作的基线与指导书一致。

   > <font size=2>注意：进行过项目 1 第一周练习的同学，这步应该已经具备，直接从第 2 步开始。</font>

2. 建立并切换到分支 week2_base：

   ```bash
   git checkout main
   git checkout -b week2_base
   ```

   这个分支对应**基本实验**。开始实验时，每完成一个，就 commit  一次，commit msg 是 "step N"，N 是实验序号。

3. 建立并切换到分支 week2_exercise：

   ```bash
   git checkout main
   git checkout -b week2_exercise
   ```

   这个分支对应**附加练习**。根据每个附加练习的要求完成，每完成一个，commit 一次，commit msg 是 "exercise N"，N 是练习序号。

4. 执行 `make run ARCH=riscv64` 测试一下环境，我们的实习平台是 **riscv64-qemu-virt**。

   ```bash
          d8888                            .d88888b.   .d8888b.
         d88888                           d88P" "Y88b d88P  Y88b
        d88P888                           888     888 Y88b.
       d88P 888 888d888  .d8888b  .d88b.  888     888  "Y888b.
      d88P  888 888P"   d88P"    d8P  Y8b 888     888     "Y88b.
     d88P   888 888     888      88888888 888     888       "888
    d8888888888 888     Y88b.    Y8b.     Y88b. .d88P Y88b  d88P
   d88P     888 888      "Y8888P  "Y8888   "Y88888P"   "Y8888P"
   
   arch = riscv64
   platform = riscv64-qemu-virt
   target = riscv64gc-unknown-none-elf
   smp = 1
   build_mode = release
   log_level = warn
   
   Hello, world!
   ```

   看到这个输出表示环境正常。
