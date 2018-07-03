---
title: 将警报的订阅添加和编辑订阅页面 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b843bde8905d8b6803dda56a6370f70c934a610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013446"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a>将警报的订阅添加和编辑订阅页面
添加警报订阅和编辑订阅页的类似。 它们不同，编辑订阅页显示的订阅者 ID （Microsoft Windows 的当前门户用户帐户），并且具有一组不同的按钮。 图 1 显示了添加警报订阅和编辑订阅页。  

 ![添加警报编辑订阅](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")  

 **图 1**  

 **ESB 管理门户添加警报订阅和编辑订阅页**  

 添加警报订阅和编辑订阅页面允许您指定并修改以下：  

- 要使用的订阅 （而不是 Microsoft Windows 帐户电子邮件地址） 的自定义电子邮件地址  

- 如果将接受警报通知的时间段  

- 事件，例如休假"买卖"期  

- 通过该门户不会发送重复警报间隔  

  您可以执行以下操作在添加警报订阅和编辑订阅页上：  

- 选中复选框旁边**自定义电子邮件**文本框如果想要使用标准 Windows 帐户在电子邮件地址，不同的订阅的电子邮件地址，然后在文本框中键入的首选电子邮件地址。  

- 选择顶部的复选框**计划**部分中如果你想要指定在段时在门户应将警报发送到你，，然后指定中时间段的开始和结束时间**开始时间**和**结束时间**下拉列表。 超出此时间段发生的警报排队，并在指定时段内传送。  

- 键入开始日期和结束日期**买卖期**是否存在时将不能接收和处理警报在一段。 使用两个日期，格式为 mm/dd/yyyy。  

- 选择**间隔**中**分钟**和多个实例的同一个警报发生时发送只有一个的比较引发的警报在门户将过程。 这可以防止出现一次快速故障创建大量的相同警报消息。  

- 单击**保存**按钮以创建或更新订阅。  

- 单击**删除**按钮 （仅适用于编辑订阅页） 以删除所选的订阅。  

- 单击**取消**按钮以返回到[警报查看器页](../esb-toolkit/alert-viewer-page.md)无需创建或修改订阅。
