---
title: 配置时区和重复周期在 BizTalk Server 中计划 |Microsoft Docs
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe12e4fe81705d178520f02591f8179e47606f6c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753285"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a>配置时区和重复执行计划在 BizTalk Server 中
将时区设置和配置重复计划在应用中接收位置[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 上的高级计划功能接收位置包括一些选项。 使用高级计划选项，设置时区，并且还设置重复执行计划。

本主题演示如何配置这些功能。

## <a name="prerequisites"></a>必要條件
安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="time-zone"></a>时区

**计划**接收位置的属性包括**时区**属性。 设置时，而不是本地计算机上的时区使用接收位置中选择的时区。 

所有日期和时间中的**计划**属性是特定于您选择的时间区域。 任何现有计划将迁移到 BizTalk 管理数据库 (BizTalkMgmtDb) 的宿主服务器的时区。 

您还可以调整为夏令时 (DST)。 选中后，计划将自动调整为夏时制的时间区域选择。 此选项没有任何影响计划如果：

* 指定的时区不具有夏时制
* 在您选择的时间区域中未观察到夏时制

## <a name="enable-recurrence-schedule"></a>启用重复计划
1. 在中**BizTalk Server 管理**控制台中，右键单击其中一个将接收位置，然后选择**属性**。 
2. 上**计划**页上，选择**启用服务时段**。 **开始时间**并**停止时间**设置计划允许运行的初始时间：

    ![启用服务 Windows 为接收端口](../core/media/enable-service-windows-for-receive-port.PNG)

3. 将显示其他计划选项：

    ![高级计划的接收端口](../core/media/advanced-scheduling-for-receive-port.PNG)

4. **重复周期**属性在运行每个天、 周或月所选的接收端口： 

    1. 使用**每日**定期运行的接收端口每*x*数天，在启动**从**日期选择，并仅在**服务时段**你选择：

        ![每日计划](../core/media/daily-schedule.png)

    2. 使用**每周**重复一周中并仅在特定的一天中运行的接收端口**服务时段**你选择： 

        ![每周计划](../core/media/weekly-schedule.png)

    3. 使用**每月**重复周期每月计划上运行的接收端口。 **天**并**上**选项才可用。 
    
        使用**天**重复周期在特定的日期内运行的接收端口**月**你选择： 

        ![每月计划](../core/media/monthly-schedule.PNG)

        使用**上**重复周期的每月特定天运行的接收端口：

        ![每月按计划](../core/media/monthly-on-schedule.PNG)

5. 单击“确定”保存更改。 

## <a name="see-also"></a>请参阅
[配置功能包](../core/configure-the-feature-pack.md)
