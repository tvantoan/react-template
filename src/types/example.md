//global.d.ts

/// <reference types="vite/client" />

declare module "\*.svg" {
const content: string
export default content
}

//common.ts

export interface Pagination {
page: number
limit: number
total: number
}

export interface ApiResponse<T> {
data: T
message: string
}

//env.d.ts

interface ImportMetaEnv {
readonly VITE_API_URL: string
readonly VITE_APP_NAME?: string
}

interface ImportMeta {
readonly env: ImportMetaEnv
}
