---
title: 错误设置页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f10b8b-9a32-40ca-9ce4-0b69e159c36c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ce03e5284122e8c1de9bd4e5c2d69c392174e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294141"
---
# <a name="fault-settings-page"></a>“错误设置”页
图 1 显示的错误设置页。 此页显示了一系列的可修改的管理设置。  
  
 ![错误设置页](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8 FaultSettingsPage")  
  
 **图 1**  
  
 **ESB 管理门户错误设置页**  
  
 以下列表说明如何使用 ESB 管理门户错误设置页的功能：  
  
-   若要更改的审核选项，选择你要审核每个事件对应的复选框。 当重新提交错误时，可用的事件将非常保存修改后的设置，编辑和失败后成功重新提交错误。  
  
-   门户维护 Portal Alert 服务生成的警报的队列。 你可以修改此服务中设置**警报队列选项**页的部分。 可以启用或禁用服务，指定与 Microsoft Active Directory 目录服务，其交互和控制的队列批大小和轮询间隔。  
  
-   若要更改的警报的电子邮件服务的设置，请使用中的控件**警报的电子邮件选项**页的部分。 你可以启用或禁用该服务;指定电子邮件服务器和的"发件人"地址;更改轮询间隔和批处理大小;并指定服务使用的 XSLT 文件的路径。  
  
> [!NOTE]
>  安装和配置 ESB 门户和 Portal Alert 服务时，你必须在此页中输入值。 有关详细信息，请参阅[安装 ESB 管理门户](http://go.microsoft.com/fwlink/?LinkId=188554)。