---
title: "配置的时区和重复计划在 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: "5"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 918d12e2dc96723327f4d0b0d2b0f0d435d6e42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a>配置的时区和 BizTalk Server 中的重复执行计划
时区上并配置重复计划你接收中的位置[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**上的高级计划功能接收位置包含一些选项。 使用高级的计划选项，设置时区，并且还设置重复执行计划。

本主题演示如何配置这些功能。

## <a name="prerequisites"></a>先决条件
安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="time-zone"></a>时区

**计划**接收位置的属性包括**时区**属性。 设置时，而不是本地计算机上的时区使用你在接收位置中选择的时区。 

所有日期和时间在**计划**属性是特定于你选择的时区。 任何现有计划迁移到承载 BizTalk 管理数据库 (BizTalkMgmtDb) 的服务器的时区。 

你还可以调整为夏令时 (DST)。 选中后，计划将自动调整为你选择的时区的夏时制。 如果组件，此选项可对计划没有任何影响：

* 指定的时区没有夏时制
* 夏时制未观察到在你选择的时区

## <a name="enable-recurrence-schedule"></a>启用重复执行计划
1. 在**BizTalk Server 管理**控制台中，右键单击其中一个你接收位置，然后选择**属性**。 
2. 上**计划**页上，选择**启用服务窗口**。 **开始时间**和**停止时间**设置允许运行计划的初始时间：

    ![启用的服务时段接收端口](../core/media/enable-service-windows-for-receive-port.PNG)

3. 显示的其他计划选项：

    ![有关高级计划接收端口](../core/media/advanced-scheduling-for-receive-port.PNG)

4. **重复**属性运行每个天、 周或月你选择的接收端口： 

    1. 使用**每日**重复运行接收端口每个*x*数天上, 启动**从**日期选择，并仅在**服务时段**你选择：

        ![每日计划](../core/media/daily-shcedule.png)

    2. 使用**每周**重复上一周内，就能仅在特定的一天运行接收端口**服务窗口**你选择： 

        ![每周计划](../core/media/weekly-shcedule.png)

    3. 使用**每月**定期在每月计划上运行的接收端口。 **天**和**上**选项才可用。 
    
        使用**天**重复周期内的特定日期运行接收端口**月**你选择： 

        ![每月计划](../core/media/monthly-shcedule.PNG)

        使用**上**重复执行的特定天的月份上运行的接收端口：

        ![每月按计划](../core/media/monthly-on-shcedule.PNG)

5. 单击“确定”保存更改。 

## <a name="see-also"></a>另请参阅
[配置功能包](../core/configure-the-feature-pack.md)