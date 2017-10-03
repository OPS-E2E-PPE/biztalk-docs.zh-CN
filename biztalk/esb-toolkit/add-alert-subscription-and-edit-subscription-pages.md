---
title: "警报订阅中添加和编辑订阅页面 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49bed9959b51439f21d625795a69804fd41d77ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a>警报订阅中添加和编辑订阅页面
添加警报订阅和编辑订阅页很相似。 它们不同，因为编辑订阅页显示订阅服务器 ID （Microsoft Windows 当前门户用户的帐户），并具有一组不同的按钮。 图 1 显示的添加警报订阅和编辑订阅页。  
  
 ![添加警报编辑订阅](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8 AddAlertEditSubscription")  
  
 **图 1**  
  
 **ESB 管理门户添加警报订阅和编辑订阅页**  
  
 添加警报订阅和编辑订阅页允许你指定并修改以下：  
  
-   要使用的订阅 （而不是你的 Microsoft Windows 帐户电子邮件地址） 的自定义电子邮件地址  
  
-   如果将接受警报通知的时间段  
  
-   如假期的事件"买卖"期  
  
-   通过该门户不会发送重复警报间隔  
  
 你可以执行以下操作的添加警报订阅和编辑订阅页上：  
  
-   选中的复选框旁边**自定义电子邮件**文本框中，如果你想要使用标准 Windows 帐户在电子邮件地址，不同的订阅的电子邮件地址，然后在文本框中键入首选电子邮件地址。  
  
-   选择顶部的复选框**计划**部分如果你想要指定当门户应将警报发送到你，，然后指定期的开始和结束时间的段**开始时间**和**结束时间**下拉列表。 发生此期之外的警报排队，并在指定时段内传递。  
  
-   键入的开始日期和结束日期**黑色超时期限**是否存在一段时间，当你将无法接收和处理的警报。 用于在两个日期的格式为 mm/dd/yyyy。  
  
-   选择**间隔**中**分钟**和相同警报的多个实例发生时发送只有一个的比较引发警报门户将过程。 这可以防止创建大量的相同警报消息快速出现错误。  
  
-   单击**保存**按钮以创建或更新订阅。  
  
-   单击**删除**按钮 （仅适用于编辑订阅页） 以删除所选的订阅。  
  
-   单击**取消**按钮以返回到[警报查看器页面](../esb-toolkit/alert-viewer-page.md)而不创建或修改订阅。