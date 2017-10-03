---
title: "适配器组和组适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e0a9423-99dd-4474-afa1-fd8e1d074cd1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcf10f50857026893245cc567783b649f614c4f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-groups-and-group-adapters"></a>适配器组和组适配器
*适配器组*是一种管理机制，可用于收集和组织的适配器集。 与此相反，*组适配器*是服务的适配器组中的所有适配器的组件。 例如，您可以编写一组全部使用相同的 COM 组件，通过 TCP/IP 传输密码同步的适配器。 这一组适配器称为适配器组，而为所有这些适配器提供服务的组件称为组适配器。 适配器组在配置存储中进行描述。 你可以通过使用来检索信息和适配器组上的更新`ISSOPSAdapter.ReceiveNotification`。  
  
 组适配器与适配器组同名。 除了命名限制之外，组适配器在其他方面与普通的适配器是相同的。 例如，组适配器可以具有其配置文件中所描述的独立的访问组和配置属性。 组适配器很可能与适配器组中的某个适配器位于同一台计算机上。 不过，目前这并不是强制性的规定。 同样，同一适配器组中的所有适配器可以位于同一台计算机上。  
  
 通过使用`ISSOPSAdapter.InitializeAdapter`，您可以访问并在启动期间初始化组适配器。 在初始化组适配器时，系统会通知当前系统上的适配器组中所有适配器的组适配器。 此外，在适配器组中添加、删除、启用或禁用适配器时，系统将向组适配器发送通知。 不过，组适配器不接收任何密码更改通知。  
  
 适配器组和组适配器均可使用管理工具进行选择。  
  
## <a name="see-also"></a>另请参阅  
 [密码同步适配器](../core/password-sync-adapters.md)