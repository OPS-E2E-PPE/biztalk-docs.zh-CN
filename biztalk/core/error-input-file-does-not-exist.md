---
title: 错误-输入的文件不存在 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e825ba6d0046e3be686cd155b5a8892a5ae8b99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388806"
---
# <a name="error---input-file-does-not-exist"></a>错误-输入的文件不存在
**错误代码**  
  
 btm1037  
  
 **说明**  
  
 为测试映射操作不存在，且测试映射输入的类型未设置为指定的输入的实例消息文件**生成实例**。 时的值**测试映射输入**映射属性未设置为**生成实例**，必须指定现有实例消息文件**测试映射输入实例**将属性映射。  
  
 **用户执行任何操作**  
  
 根据需要，设置一个或多个以下映射属性：  
  
-   **测试映射输入实例。** 右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**对话框的映射，请单击省略号 （**...**) 中的值字段按钮**测试映射输入实例**属性。 使用**选择输入文件**对话框中，选择现有的实例消息与映射的源架构一致的文件。 或者，直接的值字段中键入此文件的路径**测试映射输入实例**属性。  
  
-   **测试映射输入。** 若要避免指定输入的实例消息文件，右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡**属性页**的映射中，使用下拉列表中的值字段对话框**测试映射输入**属性选择**生成实例**。 在这种情况下，您需要指定的文件**测试映射输入实例**属性。