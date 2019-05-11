---
title: 容错设置页 |Microsoft Docs
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
ms.openlocfilehash: f1129d0eb8894c777a76e129a3777cd0757594f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250167"
---
# <a name="fault-settings-page"></a>错误设置页
图 1 显示了容错设置页。 此页显示一系列的管理设置，可以修改它。  
  
 ![错误设置页](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8-FaultSettingsPage")  
  
 **图 1**  
  
 **ESB 管理门户错误设置页**  
  
 以下列表说明了如何使用 ESB 管理门户错误设置页的功能：  
  
-   若要更改的审核选项，选择你想要审核每个事件对应的复选框。 可用的事件。 保存修改的设置，编辑和失败后成功重新提交错误时重新提交错误  
  
-   在门户保留 Portal Alert 服务生成的警报的一个队列。 您可以修改此服务中的设置**警报队列选项**页部分。 可以启用或禁用服务、 指定与 Microsoft Active Directory 目录服务交互，控制队列批大小和轮询间隔。  
  
-   若要更改警报的电子邮件服务的设置，请使用中的控件**警报的电子邮件选项**页部分。 可以启用或禁用该服务;指定电子邮件服务器和"发件人"地址;更改轮询间隔和批大小;并指定该服务使用的 XSLT 文件的路径。  
  
> [!NOTE]
>  安装和配置 ESB 门户和门户通知服务时，必须在此页中输入值。 有关详细信息，请参阅[安装 ESB 管理门户](http://go.microsoft.com/fwlink/?LinkId=188554)。