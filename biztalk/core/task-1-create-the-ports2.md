---
title: 任务 1： 创建 Ports2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097504c3-67de-4a0b-99a5-648121aff1e5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41f02d464b15841c3f5a00dbd0601f65e18b510
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278837"
---
# <a name="task-1-create-the-ports"></a>任务 1： 创建端口
创建以下端口，BeginDoc 和 EndDocOut 位于左侧，具有 3 个操作的 JDEPort 位于右侧。  
  
|名称和设置|运算|消息类型 > 架构|  
|-----------------------|---------------|--------------------------|  
|BeginDoc<br /><br /> BeginDocType/单向/内部<br /><br /> 我将始终被在此端口上接收消息<br /><br /> 以后指定|操作 1 请求 -|BeginDocTest.B4200310Service_1。<br />F4211FSBeginDoc|  
|EndDocOut<br /><br /> EndDocType/单向/内部<br /><br /> 我将始终在此端口上发送消息<br /><br /> 以后指定|操作 1 请求 -|BeginDocTest.B4200310Service_1。<br />F4211FSEndDocResponse|  
|JDEPort<br /><br /> JDEPortType/请求-响应/内部<br /><br /> 我将始终发送请求并接收响应<br /><br /> 指定以后**注意：** 的更多操作，右键单击端口，然后选择**新操作**。|操作 1 请求 -<br /><br /> 操作 1 响应 -<br /><br /> 操作 2 的请求-<br /><br /> 操作 2 响应-<br /><br /> 操作 3 请求-<br /><br /> 操作 3 响应-|BeginDocTest.B4200310Service_1。<br />F4211FSBeginDoc<br /><br /> BeginDocTest.B4200310Service_1。<br />F4211FSBeginDocResponse<br /><br /> BeginDocTest.B4200310Service_1。<br />F4211FSEditLine<br /><br /> BeginDocTest.B4200310Service_1。<br />F4211FSEditLineResponse<br /><br /> BeginDocTest.B4200310Service_1。<br />F4211FSEndDoc<br /><br /> BeginDocTest.B4200310Service_1。<br />F4211FSEndDocResponse|  
  
## <a name="see-also"></a>另请参阅  
 [任务 2： 创建消息](../core/task-2-create-the-messages1.md)   
 [任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape2.md)   
 [任务 5： 配置转换形状](../core/task-5-configure-the-transform-shape1.md)