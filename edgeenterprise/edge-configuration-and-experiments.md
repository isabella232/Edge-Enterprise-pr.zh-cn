---
title: Microsoft Edge 配置和实验
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 配置和实验
ms.openlocfilehash: aef19fd9c119926a934a1ab00009a89ce2fe31fc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447766"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a>Microsoft Edge 配置和实验

本文介绍了 Microsoft Edge 与实验和配置服务 (ECS) 之间的交互。 Microsoft Edge 与此服务通信以请求和接收不同种类的负载。 这些负载包括配置、功能展示和实验。

> [!IMPORTANT]
> 确保客户端能够访问 `https://config.edge.skype.com` 以能够接收到负载。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="configurations"></a>配置

配置是用于确保产品运行状况、安全性和隐私合规性的有效负载，旨在对所有用户都提供相同的值（基于平台和频道）。这可能是为域操作启用功能标志，也可用于在出现 bug 时禁用功能标志。

## <a name="controlled-feature-rollout"></a>受控功能推出

受控功能推出 (CFR) 是一种缓慢增加接收功能的用户组规模的过程。 通过将新功能分配给随机选择的一部分用户，可以将用户反馈与大小相同且无该功能的对照组进行比较，以评估该功能的影响。

## <a name="experiments"></a>试验

Microsoft Edge 版本具有仍在开发或实验中的特性和功能。 实验类似于 CFR，但用户组更小，以便于测试新概念。 这些功能默认情况下将隐藏，直到推出该功能或实验结束为止。 实验标志用于启用和禁用这些功能。

## <a name="about-the-ecs"></a>关于 ECS

在上述所有场景下，该服务都会将功能标志值传递给浏览器客户端，以便可以应用这些值。 将立即应用配置，或者在用户重启浏览器时立即应用配置，具体取决于更新。

Microsoft Edge 与该服务的交互受 [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) 策略中的设置控制。 你可以将策略设置配置为：

- 仅检索配置
- 检索配置和实验
- 禁止与服务通信

  > [!CAUTION]
  > 如果你禁止与服务通信，这将影响 Microsoft 及时处理严重 bug 的能力。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://www.microsoftedgeinsider.com/enterprise)
- [Microsoft Edge 文档登录页面](./index.yml)