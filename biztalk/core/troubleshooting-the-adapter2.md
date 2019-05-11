---
title: 故障排除 Adapter2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 556cf4eea03af072e5b42a5748482c4e60a5a5d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306404"
---
# <a name="troubleshooting-the-adapter"></a>适配器疑难解答
本主题包含了一些信息，可帮助您识别和解决可能会在使用用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器时遇到的问题。  
  
## <a name="cannot-use-wildcard-characters-in-send-port-properties"></a>无法在发送端口配置中使用通配符  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器不支持在以下发送端口属性字段中使用通配符：  
  
-   用户名  
  
-   App Server Path  
  
-   Java_Home  
  
-   People JAR Files  
  
## <a name="getxml-data-assigns-0001-01-01-value-for-null-dates"></a>Get.xml 数据为空日期分配 0001-01-01 值  
 Get.xml 不正确地为空日期分配 0001-01-01 值。 如果希望使用空值替换 0001-01-01，则必须使用 BizTalk 映射器工具。  
  
## <a name="creating-and-updating-properties-with-collections-fails"></a>创建和更新带有集合的属性失败  
 使用 PeopleSoft 版本 8.17.02 的适配器时，适配器可以从 PeopleSoft 服务器中正确地读取数据。 但是，创建和更新带有集合的属性将失败。 这个已知 PeopleSoft 问题可能会在 PeopleSoft 将来的版本中得到解决。  
  
## <a name="see-also"></a>请参阅  
 [PeopleSoft 疑难解答](../core/troubleshooting-peoplesoft.md)