---
title: 错误-本机的输入的文件不存在 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333849007c808a20130f10dfb1f22a756024a4c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-input-file-does-not-exist"></a>错误-本机的输入的文件不存在
**错误代码**  
  
 btm1040  
  
 **说明**  
  
 为测试映射操作指定的本地输入实例消息文件不存在。 时的值**测试映射输入**映射属性设置为**本机**，必须指定现有的本地实例消息文件进行**测试映射输入实例**映射属性。  
  
 **用户执行任何操作**  
  
 右键单击解决方案资源管理器中的相关映射，请单击**属性**，然后在**测试映射**选项卡中**属性页**对话框中的地图中，单击省略号 （**...**) 的值字段中的按钮**测试映射输入实例**属性。 在**选择输入文件**对话框中，选择现有的本机实例符合映射的源架构的消息文件。 或者，直接的值字段中键入此本机文件的路径**测试映射输入实例**属性。