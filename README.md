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
3. [Business Hours Only](#3-business-hours-only)
4. [All Hours](#4-all-hours)
5. [Alert](#5-alert)
6. [Responding To Alerts](#6-responding-to-alerts)
7. [Security Considerations](#7-security-considerations)

## 1. Introduction

People operate within sociotechnical systems. As part of participation in a sociotechnical system, people consume communications from technical subsystems. How this information is organized and processed impacts a person's ability to understand, contextualize, and respond appropriately. This document presents three categories of communication along with recommendations for how a person should act and how they should process each communication category.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [BCP 14](https://tools.ietf.org/html/bcp14) [[RFC2119](https://tools.ietf.org/html/rfc2119)] [[RFC8174](https://tools.ietf.org/html/rfc8174)] when, and only when, they appear in all capitals, as shown here. 

The key words “WARNING”, “CAUTION”, and “NOTE” in this document are to be interpreted as described in [[CRFC1](https://github.com/corporate-rfc/CRFC1)] when, and only when, they appear in all capitals, as shown here.

## 2. Logs

The category of Logs includes system logs, application logs, traffic logs, metrics, traces, health checks, and other types of telemetry. Logs are a non-actionable communication. 

Logs SHALL NOT require human action. Logs SHALL NOT generate alerts.

Logs MAY be stored in case a person wants to look at them later in order to gain a deeper understanding of the system (for example: while troubleshooting or debugging).

## 3. Business Hours Only

The category of Business Hours Only is a communication indicating that the system requires human intervention in the future, but can wait until business hours. The assumption is that the system is maintaining its objectives and agreements, however, the system predicts that it will not be able to continue to maintain its objectives and agreements without human intervention at some later date.

Business Hours Only communication SHALL NOT generate alerts.

In order to process Business Hours Only communication, it SHOULD be reviewed at a regular cadence that is appropriate for timely action.

_CAUTION: If Business Hours Only communication is not reviewed at an appropriate regular cadence, it may result in violation of system objectives or system agreements._

NOTE: If a system is producing a Business Hours Only communication, it is an opportunity for improvement. An ideal system design would not have Business Hours Only communications. In practice, Business Hours Only communications highlight existence of human-level tasks that may be difficult to automate.

## 4. All Hours

The category of All Hours is an emergency communication. The system requires immediate human intervention because a system objective or a system agreement was violated or imminently will be. 

All Hours communication SHALL generate alerts.

NOTE: All Hours communication can happen at any time, during business hours, or outside business hours.

## 5. Alert

Alert is an emergency communication that is intended to interrupt normal operations and introduce a shift in focus toward the subject of emergency communication.

## 6. Responding To Alerts

Alerts SHALL consist only of All Hours communications. Alerts SHALL be actionable. If an alert is received, it is always an indication of failure. The failure is either of the system or the alert trigger itself. Upon receipt of an alert, the action is either to recover the system to normal operation, change the alert trigger to be actionable in the future, replace the alert with Business Hours Only or Logs communications, or delete the alert.

## 7. Security Considerations

There are no known security considerations.

## Acknowledgments

The described model is not novel to this document. However, the author no longer recalls the original source of this model.

## Author's Address

Tristan Slominski

Email: tristan.slominski@gmail.com
