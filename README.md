<div align="center">

  <img src="https://github.com/adrianhajdin/zoom-clone/assets/67959015/f09a8421-67d3-45ce-b9bc-a791cdc2774b" alt="YOOM project banner" />

  <br />

  <img src="https://img.shields.io/badge/-TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/-Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/-Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/-Clerk-6C47FF?style=for-the-badge&logo=clerk&logoColor=white" alt="Clerk" />
  <img src="https://img.shields.io/badge/-Stream-005FFF?style=for-the-badge&logo=stream&logoColor=white" alt="Stream" />

  <h1>YOOM</h1>

  <p>A real-time video meeting app for instant calls, scheduled meetings, screen sharing, and recordings.</p>

</div>

## Table of contents

1. [Introduction](#introduction)
2. [Tech stack](#tech-stack)
3. [Features](#features)
4. [Quick start](#quick-start)
5. [Environment variables](#environment-variables)
6. [Project structure](#project-structure)

## Introduction

YOOM lets people sign in, start or join a meeting, and use the usual meeting controls: camera, microphone, screen share, reactions, recording, and participant management. Authentication is handled by Clerk. Live video is handled by Stream.

## Tech stack

- [Next.js](https://nextjs.org/) 14 and React 18
- TypeScript
- [Clerk](https://clerk.com/) for authentication
- [Stream Video](https://getstream.io/video/) for calls
- [shadcn/ui](https://ui.shadcn.com/) and [Tailwind CSS](https://tailwindcss.com/)

## Features

- **Authentication.** Sign in with email or a social provider, with protected meeting routes.
- **Instant meeting.** Start a call and set camera and microphone before joining.
- **Meeting controls.** Record, react, share a screen, mute, change layout, and manage participants.
- **Leave or end.** Participants can leave. The host can end the meeting for everyone.
- **Schedule.** Pick a date and time. Upcoming meetings can be shared or started from the dashboard.
- **History.** Review past meetings and open recordings.
- **Personal room.** Each account has a stable meeting link.
- **Join by link.** Enter a meeting link to join someone else's call.
- **Responsive layout.** The dashboard and meeting UI adapt to smaller screens.

## Quick start

**Prerequisites**

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) 18 or newer
- [npm](https://www.npmjs.com/)

**Clone and install**

```bash
git clone https://github.com/AbhinavBhushan096/yoom.git
cd yoom
npm install
```

**Configure credentials**

```bash
cp .env.example .env.local
```

Fill in `.env.local` with your Clerk and Stream keys. See [Environment variables](#environment-variables).

**Run**

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Environment variables

Copy `.env.example` to `.env.local`. Do not commit `.env.local`.

| Variable | Required | Where to get it |
| --- | --- | --- |
| `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` | Yes | [Clerk Dashboard](https://dashboard.clerk.com) → API keys |
| `CLERK_SECRET_KEY` | Yes | Clerk Dashboard → API keys |
| `NEXT_PUBLIC_CLERK_SIGN_IN_URL` | Yes | Use `/sign-in` |
| `NEXT_PUBLIC_CLERK_SIGN_UP_URL` | Yes | Use `/sign-up` |
| `NEXT_PUBLIC_STREAM_API_KEY` | Yes | [Stream Dashboard](https://dashboard.getstream.io) → your app → API keys |
| `STREAM_SECRET_KEY` | Yes | Stream Dashboard → your app → API keys |
| `NEXT_PUBLIC_BASE_URL` | Yes | `http://localhost:3000` locally, or your deployed URL |

`NEXT_PUBLIC_BASE_URL` is used to build invite links. It must not have a trailing slash.

## Project structure

```text
app/            Routes for auth, home, and meetings
actions/        Server actions (Stream tokens)
components/     UI, meeting room, and dashboard cards
constants/      Shared constants
hooks/          Stream call queries
lib/            Utilities
providers/      Stream client provider
public/         Icons and images
```
