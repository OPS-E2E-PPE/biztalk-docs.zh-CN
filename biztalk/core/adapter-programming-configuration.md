---
title: 适配器编程配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b407c6f0239798110b7b971ffa4febd58d6f70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361335"
---
# <a name="adapter-programming-configuration"></a>适配器编程配置
每种类型的密码同步适配器具有不同的配置要求，具体取决于设计适配器所针对的哪些非 Windows 系统。 关联应用程序，正如可以使用企业单一登录配置存储区来集中和更安全地存储配置属性。  
  
 如使用其他配置存储应用程序，管理员可以使用企业单一登录管理用户界面来查找和读取描述您的适配器的配置属性的 XML 文件。 管理工具使用 XML 文件呈现属性页来收集所需的属性值，指定的适配器。 此外可以使用 ISSOConfigStore 加载和读取 XML 名称/值组合到和从配置存储区，或者可以使用 SSOPS 工具。  
  
 此外可以使用企业单一登录管理工具来启用和禁用适配器。 在初始创建时，适配器处于禁用状态。  
  
## <a name="see-also"></a>请参阅  
 [密码同步适配器](../core/password-sync-adapters.md)