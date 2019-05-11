---
title: 适配器组和组适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e0a9423-99dd-4474-afa1-fd8e1d074cd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33cba4d210f79072f5f36a0a47e8546b2d2db265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361451"
---
# <a name="adapter-groups-and-group-adapters"></a>适配器组和组适配器
*适配器组*是一种管理机制，可用于收集和组织一组适配器。 与此相反，*组适配器*是服务适配器组中的所有适配器的组件。 例如，您可能编写的适配器集所有使用相同的 COM 组件通过 TCP/IP 传输密码同步。 适配器称为适配器组，而所有这些服务的组件称为组适配器。 适配器组所述配置存储区。 可以通过使用检索信息和更新有关适配器组`ISSOPSAdapter.ReceiveNotification`。  
  
 组适配器已与适配器组相同的名称。 以外的命名限制，组适配器在其他方面与普通的适配器。 例如，组适配器可以具有独立的访问组和配置属性，如其配置文件中所述。 组适配器很有可能与适配器组中的任何适配器所在的计算机上。 但是，这是不是当前实施的。 同样，可以预期相同的适配器组中所有适配器可在同一计算机上。  
  
 通过使用`ISSOPSAdapter.InitializeAdapter`，可以访问并在启动期间初始化组适配器。 在初始化组适配器时，系统会通知当前系统上的适配器组中的所有适配器的组适配器。 此外，系统将通知发送到组适配器适配器是添加、 删除、 启用或禁用适配器组中的任何时间。 但是，组适配器不接收任何密码更改通知。  
  
 适配器组和组适配器是可选使用管理工具。  
  
## <a name="see-also"></a>请参阅  
 [密码同步适配器](../core/password-sync-adapters.md)