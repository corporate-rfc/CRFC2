Corporate RFC<br/>
Corporate Request For Comments: 2

Tristan Slominski

September 2020

# System to Human Communication

## Abstract

This document describes a model for thinking about how systems communicate with humans. It enumerates categories of communications and provides recommendations for how each category of communication should be processed.

## Status of this Memo

This document is published to describe a model of operation.

## Copyright Notice

Copyright (c) 2020 the persons identified as the document authors. All rights reserved.

## Table of Contents

1. [Introduction](#1-introduction)
2. [Logs](#2-logs)
3. [Do It Now](#3-do-it-now)
4. [Do It Later](#4-do-it-later)
5. [Responding To Alerts](#5-responding-to-alerts)
6. [Security Considerations](#6-security-considerations)

## 1. Introduction

People operate within sociotechnical systems. As part of participation in a sociotechnical system, people consume communications from technical subsystems. How this information is organized and processed impacts a person's ability to understand, contextualize, and respond appropriately. This document presents three categories of communication along with recommendations for how a person should act and how they should process each communication category.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [BCP 14](https://tools.ietf.org/html/bcp14) [[RFC2119](https://tools.ietf.org/html/rfc2119)] [[RFC8174](https://tools.ietf.org/html/rfc8174)] when, and only when, they appear in all capitals, as shown here. 

The key words “WARNING”, “CAUTION”, and “NOTE” in this document are to be interpreted as described in [[CRFC1](https://github.com/corporate-rfc/CRFC1)] when, and only when, they appear in all capitals, as shown here.

## 2. Logs

The category of Logs includes system logs, application logs, traffic logs, metrics, traces, health checks, and other types of telemetry. Logs are a non-actionable communication. 

Logs SHALL NOT require human action. Logs SHALL NOT generate alerts.

Logs MAY be stored in case a person wants to look at them later in order to gain a deeper understanding of the system (for example: while troubleshooting or debugging).

## 3. Do It Now

The category of Do It Now is an emergency communication. The system requires immediate human intervention because a service level objective or a service level agreement was violated or imminently will be.

Do It Now communication SHALL generate alerts.

## 4. Do It Later

The category of Do It Later is a communication indicating that the system requires human intervention in the future, but not now. The assumption is that the system is maintaining its objectives and agreements, however, the system predicts that it will not be able to continue to maintain its objectives and agreements without human intervention at some later date.

Do It Later communication SHALL NOT generate alerts.

In order to process Do It Later communication, this communication should be reviewed at a regular cadence that is appropriate for timely action.

NOTE: If a system is producing a Do It Later communication, it is an opportunity for improvement. An ideal system design would not have Do It Later communications. In practice, Do It Later communications highlight existence of human-level tasks that may be difficult to automate.

## 5. Responding To Alerts

Alerts SHALL consist only of Do It Now communications. Alerts SHALL be actionable. If an alert is received, it is always an indication of failure. The failure is either of the system or the alert trigger itself. Upon receipt of an alert, the action is either to recover the system to normal operation, change the alert trigger to be actionable in the future, replace the alert with Do It Later or Logs communications, or delete the alert.

## 6. Security Considerations

There are no known security considerations.

## Acknowledgments

The described model is not novel to this document. However, the author no longer recalls the original source of this model.

## Author's Address

Tristan Slominski

Email: tristan.slominski@gmail.com