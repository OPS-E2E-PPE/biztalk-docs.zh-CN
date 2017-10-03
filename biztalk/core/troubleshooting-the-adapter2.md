---
title: "故障排除 Adapter2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991278813d2183795239d1a75c08e474b2f8159a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a>故障排除适配器
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
  
## <a name="see-also"></a>另请参阅  
 [故障排除 PeopleSoft](../core/troubleshooting-peoplesoft.md)