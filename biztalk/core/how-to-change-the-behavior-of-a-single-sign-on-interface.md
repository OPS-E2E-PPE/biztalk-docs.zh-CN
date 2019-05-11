---
title: 如何更改单一登录接口的行为 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4a4946a-e345-4c7e-835d-a3f7f72ebaca
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729b5faee2e6adff6e43a987b1defcb90450eb13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387067"
---
# <a name="how-to-change-the-behavior-of-a-single-sign-on-interface"></a>如何更改单一登录接口的行为
许多企业单一登录 (SSO) 对象模型中的对象会公开 IPropertyBag 接口，允许您修改指定的对象的行为。 如果对 SSO 对象调用 QueryInterface，可以检索 IPropertyBag 接口，并使用它来更改当前对象的行为。  

### <a name="to-change-the-behavior-for-a-specified-sso-interface"></a>若要更改指定 SSO 接口的行为  

1.  使用指定的接口上 QueryInterface 来检索 IPropertyBag 实例。  

2.  使用 IPropertyBag.Write 设置属性、 类型和接口的值。  

     下表介绍了 IPropertyBag propName 和 ptrVar 参数的有效值。  

|propName|类型|ptrValue|上可用|  
|--------------|----------|--------------|---------------|  
|CurrentSSOServer|VT_BSTR|若要将信息发送到的服务器的名称|All|  
|事务|VT_UNKNOWN<br /><br /> VT_EMPTY|一个 DTC ITransaction 指针，或者为 NULL 以清除作用域。|ISSOConfigStore::SetConfigInfo<br />ISSOConfigStore::GetConfigInfo <br />ISSOConfigStore::DeleteConfigInfo<br /><br /> ISSOAdmin::CreateApplication<br />ISSOAdmin::DeleteApplication <br />ISSOAdmin::UpdateApplication<br />ISSOAdmin::CreateFieldInfo<br /><br /> ISSOMapper::GetFieldInfo|  
|AppFilterFlags|VT_I4<br /><br /> VT_UI4|若要控制要筛选的应用程序的标志。|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AppFilterFlagsMask|VT_I4<br /><br /> VT_UI4|若要控制要筛选的应用程序的标志掩码。|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AsyncCall|VT_BOOL|为 true，则使用异步 RPC;为 false，则使用同步 RPC。|ISSOConfigOM::GetServerStatus<br /><br /> ISSOAdmin::GetGlobalInfo|  

- **CurrentSSOServer**： 用于确定哪个服务器将发送到的 SSO 信息按如下所示的标准行为：  

  1. 在当前用户的注册表中查找。 可以使用 GUI 或命令行工具的当前用户设置的服务器名称。  

  2. 查看注册表中的所有用户。 可以使用命令行工具或 GUI 的所有用户设置的服务器名称。  

  3. 如果在注册表中不找到任何 SSO 服务器名称，则使用当前计算机。  

     将 CurrentSSOServer 设置为指定的服务器将覆盖指定接口的上一过程。 设置 CurrentSSOServer 后，在接口上的所有后续方法调用将发送到指定的服务器。  

- **事务**： 指定的 DTC 事务的作用域执行的操作由 SSO 对象模型。 必须传递一个 DTC ITransaction 指针中的`ptrValue`，或"null"以清除当前事务作用域。  

- **AppFilterFlags/AppFilterMask**： 控制将哪些类型的应用程序从 ISSOMapper.GetApplications 和 ISSOMapper2.GetApplications 返回。 如果应用程序标志匹配的筛选器标志和筛选器标志掩码，则会返回由指定的标志。 执行应用程序的筛选的一种方法是将 AppFilterFlagsMask 设置为 SSO_FLAG_APP_FILTER_BY_TYPE，然后将 AppFilterFlags 设置为一个或多个以下：  

   SSO_APP_TYPE_INDIVIDUAL  

   SSO_APP_TYPE_GROUP  

   SSO_APP_TYPE_CONFIG_STORE  

   SSO_APP_TYPE_HOST_GROUP  

   SSO_APP_TYPE_PS_ADAPTER  

   SSO_APP_TYPE_PS_GROUP_ADAPTER  

- **AsyncCall**： 如果为 true，则 SSO 将执行使用异步远程过程调用 (RPC) 的方法。 该方法将返回 E_PENDING 正在进行。 任何其他返回值指示该方法已完成。 AsyncCall 还允许您进行轮询的完成情况的方法。
