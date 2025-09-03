//index.ts

import { configureStore } from "@reduxjs/toolkit"
import authReducer from "./auth.slice"
import userReducer from "./user.slice"

export const store = configureStore({
  reducer: {
    auth: authReducer,
    user: userReducer,
  },
})

export type RootState = ReturnType<typeof store.getState>
export type AppDispatch = typeof store.dispatch

//auth.slice.ts

import { createSlice, PayloadAction } from "@reduxjs/toolkit"

interface AuthState {
  token: string | null
}

const initialState: AuthState = {
  token: null,
}

const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    setToken: (state, action: PayloadAction<string>) => {
      state.token = action.payload
    },
    clearToken: (state) => {
      state.token = null
    },
  },
})

user.slice.ts

export const { setToken, clearToken } = authSlice.actions
export default authSlice.reducer


import { createSlice, PayloadAction } from "@reduxjs/toolkit"

interface User {
  id: string
  name: string
}

const initialState: User | null = null

const userSlice = createSlice({
  name: "user",
  initialState,
  reducers: {
    setUser: (_, action: PayloadAction<User>) => action.payload,
    clearUser: () => null,
  },
})

export const { setUser, clearUser } = userSlice.actions
export default userSlice.reducer
