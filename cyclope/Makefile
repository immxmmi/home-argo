SHELL := /bin/bash
.DEFAULT_GOAL := help
# ANSI Colors
RED := \033[0;31m
GREEN := \033[0;32m
YELLOW := \033[1;33m
NC := \033[0m

# ANSI Colors
RED := \033[0;31m
GREEN := \033[0;32m
YELLOW := \033[1;33m
NC := \033[0m

INTERNAL_PORT := 3000
PORT := 3001
NAMESPACE := cyclops
SERVICE_NAME := cyclops-ui

help:
	@echo "═══════════════════════════════════════════════"
	@echo "🚀 Available Commands 
	@echo "═══════════════════════════════════════════════"
	@echo ""
	@echo "  app_install                     ▶️  Install App"
	@echo "  app_port_forward                ▶️  Port-forward App to localhost"
	@echo ""
	@echo "📘 Run 'make <command>' to execute a specific task."
	@echo "═══════════════════════════════════════════════"


app_install:
	@echo "🚀 Installing App..."
	@kubectl apply -f application.yaml
	@echo -e "$(GREEN)✅ App has been installed.$(NC)"
app_port_forward:
	@kubectl port-forward svc/$(SERVICE_NAME) -n $(NAMESPACE) $(PORT):$(INTERNAL_PORT) > /dev/null 2>&1 &
	@echo "App is available at http://localhost:$(PORT)/"