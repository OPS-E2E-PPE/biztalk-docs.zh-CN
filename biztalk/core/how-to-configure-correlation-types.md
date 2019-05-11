---
title: 如何配置相关类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69770055b1d373b355bfd853e26bf463aab1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341495"
---
# <a name="how-to-configure-correlation-types"></a>如何配置相关类型
您使用**相关性属性**对话框以添加或删除相关类型属性。 相关类型列出相关集中使用的发送和接收活动，以确保与业务流程在运行时的正确实例的传入消息正确相关联的属性。  
  
 在对话框中，每个包含的属性列表有两个窗格。 左窗格中，"可用属性"包含的所有项目中定义的或它引用的属性的树视图。 默认情况下显示的属性是系统属性，BizTalk Server 定义的但还可以在属性架构中定义您自己的属性。 有关创建属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
> [!NOTE]
>  然后可以在相关类型中使用这些，则必须升级架构属性。 有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
### <a name="to-add-and-configure-a-correlation-type"></a>若要添加和配置相关类型  
  
-   在业务流程视图窗口中，右键单击**相关类型**，然后单击**新相关类型**。  
  
     **相关性属性**弹出对话框。 添加你想要在相关类型中包含的属性。  
  
    > [!NOTE]
    >  如果访问**相关性属性**对话框直接从相关集，如果尚不存在，将创建相关集相关类型。 所做的更改将保存到新的相关类型和相关集将配置为使用新的相关类型。 如果该相关集已存在相关类型并进行更改，将修改相关类型。  
  
### <a name="to-remove-a-correlation-type"></a>若要删除某一相关类型  
  
-   在业务流程视图窗口中，右键单击你想要删除，然后单击相关类型**删除**。