---
title: 启用 MS 分布式事务处理协调器，以允许 Oracle E-business Suite 的事务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0597c050e1531d71a62af04fe6c825653076297c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215069"
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a>启用 MS 分布式事务处理协调器，以允许 Oracle E-business Suite 的事务
在开始创建应用程序使用之前配置 MSDTC [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
Oracle E-business Suite 使用执行的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (通过[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型) 可以在事务范围内执行。 如果客户端程序具有多个事务的资源在同一事务的一部分，获取提升为 MSDTC 事务的事务。 若要启用的适配器执行 MSDTC 事务的范围内的操作，在运行的计算机上配置 MSDTC [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，和上 Oracle E-business Suite。 此外，添加 MSDTC 到例外列表中你的防火墙，这可能会内置的 Windows 防火墙。 
  
> [!NOTE]
>  配置 MSDTC 的步骤因个不同的操作系统而异。 本主题中列出的步骤适用于 Windows 客户端和 Windows Server 操作系统。  
  
## <a name="configure-msdtc"></a>配置 MSDTC  
  
1.  打开**组件服务**。  

    或者，在**服务器管理器**，选择**工具**，然后选择**组件服务**。  
  
2.  展开**组件服务**，展开**计算机**，展开**我的电脑**，展开**分布式事务处理协调器**，右键单击**本地 DTC**，然后选择**属性**。  
  
3.  选择 **“安全”** 选项卡。在此选项卡上，选择如下： 

  - **网络 DTC 访问**
  - **允许远程客户端** 
  - **允许入站** 
  - **允许出站** 
  - **所需的任何 Authetnication**
  
4.  单击“确定”保存更改。  
  
5.  如果系统提示您重新启动 MSDTC 服务，选择**是**。 重新启动 MSDTC 服务后，关闭属性和组件服务 MMC。 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>将 MSDTC 添加到 Windows 防火墙例外列表  

> [!TIP] 
>  Microsoft 分布式 Tansaction 处理协调器 (MSDTC) 可能已允许在防火墙中。 如果是这样，则将它列出为入站规则。 如果未列出，请使用本部分以允许 MSDTC。 

1.  打开**Windows 防火墙**，然后选择**高级设置**左侧。  

    或者，在**服务器管理器**，选择**工具**，然后选择**高级安全 Windows 防火墙**。  
  
2.  右键单击**入站规则**，然后选择**新规则**。  
  
3.  在向导中： 

    1. 选择**程序**，然后选择**下一步**。 
    2. 设置**程序路径**到`%SystemRoot%\system32\msdtc.exe`，然后选择**下一步**。  
    3. **允许连接**，然后选择**下一步**。
    4. 选择**域**，然后选择**下一步**。
    5. 输入任何名称，如`MSDTC for Oracle EBS`，然后选择**完成**。
  
5.  完成向导，并关闭 Windows 防火墙。 
  
## <a name="next"></a>Next 
[Oracle EBS 适配器的的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)